---
title: "@if"
description: "" 
date: 2022-09-24T20:58:14
tags: [""]
categories: [""]
draft: false
---

The @if rule is written @if `<expression>` { ... }, and it controls whether or not its block gets evaluated (including emitting any styles as CSS). The expression usually returns either true or false—if the expression returns true, the block is evaluated, and if the expression returns false it’s not.

```css
SCSS SYNTAX
@mixin avatar($size, $circle: false) {
  width: $size;
  height: $size;

  @if $circle {
    border-radius: $size / 2;
  }
}

.square-av {
  @include avatar(100px, $circle: false);
}
.circle-av {
  @include avatar(100px, $circle: true);
}
```

## @else

An @if rule can optionally be followed by an @else rule, written @else { ... }. This rule’s block is evaluated if the @if expression returns false.

```css
$light-background: #f2ece4;
$light-text: #036;
$dark-background: #6b717f;
$dark-text: #d2e1dd;

@mixin theme-colors($light-theme: true) {
  @if $light-theme {
    background-color: $light-background;
    color: $light-text;
  } @else {
    background-color: $dark-background;
    color: $dark-text;
  }
}

.banner {
  @include theme-colors($light-theme: true);
  body.dark & {
    @include theme-colors($light-theme: false);
  }
}
```

Conditional expressions may contain boolean operators (and, or, not).

## @else if

You can also choose whether to evaluate an @else rule’s block by writing it @else if <expression> { ... }. If you do, the block is evaluated only if the preceding @if‘s expression returns false and the @else if’s expression returns true.

In fact, you can chain as many @else ifs as you want after an @if. The first block in the chain whose expression returns true will be evaluated, and no others. If there’s a plain @else at the end of the chain, its block will be evaluated if every other block fails.

```css
@use "sass:math";

@mixin triangle($size, $color, $direction) {
  height: 0;
  width: 0;

  border-color: transparent;
  border-style: solid;
  border-width: math.div($size, 2);

  @if $direction == up {
    border-bottom-color: $color;
  } @else if $direction == right {
    border-left-color: $color;
  } @else if $direction == down {
    border-top-color: $color;
  } @else if $direction == left {
    border-right-color: $color;
  } @else {
    @error "Unknown direction #{$direction}.";
  }
}

.next {
  @include triangle(5px, black, right);
}
```

## Truthiness and Falsiness

Anywhere true or false are allowed, you can use other values as well. The values false and null are falsey, which means Sass considers them to indicate falsehood and cause conditions to fail. Every other value is considered truthy, so Sass considers them to work like true and cause conditions to succeed.

For example, if you want to check if a string contains a space, you can just write string.index($string, " "). The string.index() function returns null if the string isn’t found and a number otherwise.

> Some languages consider more values falsey than just false and null. Sass isn’t one of those languages! Empty strings, empty lists, and the number 0 are all truthy in Sass.
