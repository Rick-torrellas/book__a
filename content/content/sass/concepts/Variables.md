---
title: "Variables"
date: 2022-09-19T11:31:29
tags: [""]
categories: [""]
draft: false
---

> [offical doc](https://sass-lang.com/documentation/variables)

Para crear una variable en sass, se empieza usando el simbolo `$`.

```sass
$variable-uno: rgb(181, 4, 4);
```

Para usar esta variable necesita ser declarada en el mismo archivo o si fue creado en un partial por ejemplo, se puede usar `@use 'partial'`.

En caso de usar otro modulo, necesita espesificar el nombre del modulo. pero si no quieres espesificarlo usa `@use 'partial' as *`. 

```sass
@use 'partial'

body {
    padding: 0;
    margin: 0;
    background-color: partial.$variable-uno;
    color: white;
}
```

> Nota: es recomendable usar las variables de css, ya que estas pueden ser modificadas por javascript despues de cargar.

## ejemplo

