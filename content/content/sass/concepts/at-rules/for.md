---
title: "@for"
description: "" 
date: 2022-09-24T21:13:17
tags: [""]
categories: [""]
draft: false
---

> source: [official docs](https://sass-lang.com/documentation/at-rules/control/for)

The @for rule, written @for `<variable> from <expression> to <expression> { ... } or @for <variable> from <expression> through <expression> { ... }`, counts up or down from one number (the result of the first expression) to another (the result of the second) and evaluates a block for each number in between. Each number along the way is assigned to the given variable name. If to is used, the final number is excluded; if through is used, it's included.

```css
SCSS SYNTAX
$base-color: #036;

@for $i from 1 through 3 {
  ul:nth-child(3n + #{$i}) {
    background-color: lighten($base-color, $i * 5%);
  }
}

```
