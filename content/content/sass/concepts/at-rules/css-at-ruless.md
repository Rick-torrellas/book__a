---
title: "CSS At-Rules"
description: "" 
date: 2022-09-25T11:31:01
tags: [""]
categories: [""]
draft: false
---

Sass supports all the at-rules that are part of CSS proper. To stay flexible and forwards-compatible with future versions of CSS, Sass has general support that covers almost all at-rules by default. A CSS at-rule is written `@<name> <value>, @<name> { ... }, or @<name> <value> { ... }`. The name must be an identifier, and the value (if one exists) can be pretty much anything. Both the name and the value can contain interpolation.

```css
@namespace svg url(http://www.w3.org/2000/svg);

@font-face {
  font-family: "Open Sans";
  src: url("/fonts/OpenSans-Regular-webfont.woff2") format("woff2");
}

@counter-style thumbs {
  system: cyclic;
  symbols: "\1F44D";
}
```

If a CSS at-rule is nested within a style rule, the two automatically swap positions so that the at-rule is at the top level of the CSS output and the style rule is within it. This makes it easy to add conditional styling without having to rewrite the style rule’s selector.

```css
SCSS SYNTAX
.print-only {
  display: none;

  @media print { display: block; }
}
```

## @media

The @media rule does all of the above and more. In addition to allowing interpolation, it allows SassScript expressions to be used directly in the feature queries.

```css
SCSS SYNTAX
$layout-breakpoint-small: 960px;

@media (min-width: $layout-breakpoint-small) {
  .hide-extra-small {
    display: none;
  }
}
```

When possible, Sass will also merge media queries that are nested within one another to make it easier to support browsers that don’t yet natively support nested @media rules.

```css
@media (hover: hover) {
  .button:hover {
    border: 2px solid black;

    @media (color) {
      border-color: #036;
    }
  }
}
```

## @supports

```css
@mixin sticky-position {
  position: fixed;
  @supports (position: sticky) {
    position: sticky;
  }
}

.banner {
  @include sticky-position;
}
```

## @keyframes

The @keyframes rule works just like a general at-rule, except that its child rules must be valid keyframe rules (<number>%, from, or to) rather than normal selectors.

```css
@keyframes slide-in {
  from {
    margin-left: 100%;
    width: 300%;
  }

  70% {
    margin-left: 90%;
    width: 150%;
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}
```
