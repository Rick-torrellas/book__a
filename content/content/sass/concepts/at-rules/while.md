---
title: "@while"
description: "" 
date: 2022-09-24T21:23:34
tags: [""]
categories: [""]
draft: false
---

> source: [official web](https://sass-lang.com/documentation/at-rules/control/while)

The @while rule, written @while <expression> { ... }, evaluates its block if its expression returns true. Then, if its expression still returns true, it evaluates its block again. This continues until the expression finally returns false.

```css
@use "sass:math";

/// Divides `$value` by `$ratio` until it's below `$base`.
@function scale-below($value, $base, $ratio: 1.618) {
  @while $value > $base {
    $value: math.div($value, $ratio);
  }
  @return $value;
}

$normal-font-size: 16px;
sup {
  font-size: scale-below(20px, 16px);
}
```

> Although @while is necessary for a few particularly complex stylesheets, you’re usually better of using either @each or @for if either of them will work. They’re clearer for the reader, and often faster to compile as well.

## Truthiness and Falsiness

Anywhere true or false are allowed, you can use other values as well. The values false and null are falsey, which means Sass considers them to indicate falsehood and cause conditions to fail. Every other value is considered truthy, so Sass considers them to work like true and cause conditions to succeed.

For example, if you want to check if a string contains a space, you can just write string.index($string, " "). The string.index() function returns null if the string isn’t found and a number otherwise.

Some languages consider more values falsey than just false and null. Sass isn’t one of those languages! Empty strings, empty lists, and the number 0 are all truthy in Sass.
