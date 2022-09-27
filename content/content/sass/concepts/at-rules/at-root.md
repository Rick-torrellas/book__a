---
title: "@at-root"
description: "" 
date: 2022-09-25T11:23:42
tags: [""]
categories: [""]
draft: false
---

Lo que hace es sacar un selector que este anidado dentro de otro selector o selectores, lo lleva a la raiz del documento.

The @at-root rule is usually written @at-root <selector> { ... } and causes everything within it to be emitted at the root of the document instead of using the normal nesting. It's most often used when doing advanced nesting with the SassScript parent selector and selector functions.

For example, suppose you want to write a selector that matches the outer selector and an element selector. You could write a mixin like this one that uses the selector.unify() function to combine & with a user’s selector.

```css
@use "sass:selector";

@mixin unify-parent($child) {
  @at-root #{selector.unify(&, $child)} {
    @content;
  }
}

.wrapper .field {
  @include unify-parent("input") {
    /* ... */
  }
  @include unify-parent("select") {
    /* ... */
  }
}
```

The @at-root rule is necessary here because Sass doesn’t know what interpolation was used to generate a selector when it’s performing selector nesting. This means it will automatically add the outer selector to the inner selector even if you used & as a SassScript expression. The @at-root explicitly tells Sass not to include the outer selector.

> The @at-root rule can also be written @at-root { ... } to put multiple style rules at the root of the document. In fact, `@at-root <selector> { ... }` is just a shorthand for `@at-root { <selector> { ... } }`!

## Beyond Style Rules

On its own, @at-root only gets rid of style rules. Any at-rules like @media or @supports will be left in. If this isn’t what you want, though, you can control exactly what it includes or includes using syntax like media query features, written `@at-root (with: <rules...>) { ... }` or `@at-root (without: <rules...>) { ... }`. The (without: ...) query tells Sass which rules should be excluded; the (with: ...) query excludes all rules except those that are listed.

```css
@media print {
  .page {
    width: 8in;

    @at-root (without: media) {
      color: #111;
    }

    @at-root (with: rule) {
      font-size: 1.2em;
    }
  }
}
```

In addition to the names of at-rules, there are two special values that can be used in queries:

* rule refers to style rules. For example, @at-root (with: rule) excludes all at-rules but preserves style rules.
* all refers to all at-rules and style rules should be excluded.
