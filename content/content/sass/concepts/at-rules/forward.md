---
title: "@forward"
date: 2022-09-23T15:19:04
tags: [""]
categories: [""]
draft: false
---

Lo que te permite esta recla es cargar archivos con sus variables, funciones y mixins y reunirlos en un solo archivo, para luego ser usado con un @use o con el archivo principal final. Por lo general se usa un index para agrupar.

The @forward rule loads a Sass stylesheet and makes its mixins, functions, and variables available when your stylesheet is loaded with the @use rule. It makes it possible to organize Sass libraries across many files, while allowing their users to load a single entrypoint file.

The rule is written @forward "`<url>`". It loads the module at the given URL just like @use, but it makes the public members of the loaded module available to users of your module as though they were defined directly in your module. Those members aren’t available in your module, though—if you want that, you’ll need to write a @use rule as well. Don’t worry, it’ll only load the module once!

If you do write both a @forward and a @use for the same module in the same file, it’s always a good idea to write the @forward first. That way, if your users want to configure the forwarded module, that configuration will be applied to the @forward before your @use loads it without any configuration.

> The @forward rule acts just like @use when it comes to a module’s CSS. Styles from a forwarded module will be included in the compiled CSS output, and the module with the @forward can extend it, even if it isn’t also @used.

```CSS
// src/_list.scss
@mixin list-reset {
  margin: 0;
  padding: 0;
  list-style: none;
}
```
```css
// bootstrap.scss
@forward "src/list";
```
```css
// styles.scss
@use "bootstrap";

li {
  @include bootstrap.list-reset;
}
```

## Adding a Prefix

Because module members are usually used with a namespace, short and simple names are usually the most readable option. But those names might not make sense outside the module they’re defined in, so @forward has the option of adding an extra prefix to all the members it forwards.

This is written @forward "`<url>`" as `<prefix>-*`, and it adds the given prefix to the beginning of every mixin, function, and variable name forwarded by the module. For example, if the module defines a member named reset and it’s forwarded as list-*, downstream stylesheets will refer to it as list-reset.

```css
// src/_list.scss
@mixin reset {
  margin: 0;
  padding: 0;
  list-style: none;
}
```
```css
// bootstrap.scss
@forward "src/list" as list-*;
```
```css
// styles.scss
@use "bootstrap";

li {
  @include bootstrap.list-reset;
}
```

## Controlling Visibility

Sometimes, you don’t want to forward every member from a module. You may want to keep some members private so that only your package can use them, or you may want to require your users to load some members a different way. You can control exactly which members get forwarded by writing @forward "`<url>" hide <members...> or @forward "<url>" show <members...>`.

The hide form means that the listed members shouldn’t be forwarded, but everything else should. The show form means that only the named members should be forwarded. In both forms, you list the names of mixins, functions, or variables (including the $).

```css
// src/_list.scss
$horizontal-list-gap: 2em;

@mixin list-reset {
  margin: 0;
  padding: 0;
  list-style: none;
}

@mixin list-horizontal {
  @include list-reset;

  li {
    display: inline-block;
    margin: {
      left: -2px;
      right: $horizontal-list-gap;
    }
  }
}
```
```css
// bootstrap.scss
@forward "src/list" hide list-reset, $horizontal-list-gap;
```

## Configuring Modules

The @forward rule can also load a module with configuration. This mostly works the same as it does for @use, with one addition: a @forward rule’s configuration can use the !default flag in its configuration. This allows a module to change the defaults of an upstream stylesheet while still allowing downstream stylesheets to override them.

```css
SCSS SYNTAX
// _library.scss
$black: #000 !default;
$border-radius: 0.25rem !default;
$box-shadow: 0 0.5rem 1rem rgba($black, 0.15) !default;

code {
  border-radius: $border-radius;
  box-shadow: $box-shadow;
}
```
```css
// _opinionated.scss
@forward 'library' with (
  $black: #222 !default,
  $border-radius: 0.1rem !default
);
```
```css
// style.scss
@use 'opinionated' with ($black: #333);
```
