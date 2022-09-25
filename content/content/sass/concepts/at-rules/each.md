---
title: "@each"
description: "" 
date: 2022-09-24T21:02:52
tags: [""]
categories: [""]
draft: false
---

> source: [official docs](https://sass-lang.com/documentation/at-rules/control/each)

The @each rule makes it easy to emit styles or evaluate code for each element of a list or each pair in a map. It’s great for repetitive styles that only have a few variations between them. It’s usually written `@each <variable> in <expression>`{ ... }, where the expression returns a list. The block is evaluated for each element of the list in turn, which is assigned to the given variable name.

```css
SCSS SYNTAX
$sizes: 40px, 50px, 80px;

@each $size in $sizes {
  .icon-#{$size} {
    font-size: $size;
    height: $size;
    width: $size;
  }
}
```

## With Maps

You can also use @each to iterate over every key/value pair in a map by writing it `@each <variable>, <variable> in <expression> { ... }`. The key is assigned to the first variable name, and the element is assigned to the second.

```css
SCSS SYNTAX
$icons: ("eye": "\f112", "start": "\f12e", "stop": "\f12f");

@each $name, $glyph in $icons {
  .icon-#{$name}:before {
    display: inline-block;
    font-family: "Icon Font";
    content: $glyph;
  }
}
```

> Because @each supports destructuring and maps count as lists of lists, @each‘s map support works without needing special support for maps in particular.
