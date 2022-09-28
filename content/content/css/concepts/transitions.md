---
title: "Animating with CSS Transitions"
description: "" 
date: 2022-09-28T17:56:11
tags: [""]
categories: [""]
draft: false
---
> [source](https://www.youtube.com/watch?v=Nloq6uzF8RQ&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=8)

La manera mas basica de animar es unando las transiciones. Las transiciones te permiten definir la transicion entre dos estados de un elemento. 

En resument es el cambio del valor de las propiedades de un elemnto, entre dos estados como :hover :click, etc.

## duracion

La duracion de una transicion se puede medir en `s` segundos `ms` milisegundos, y puede declararse dentro de la propiedad `transition` o `transition-duration`.

> **Nota**: es mejor usar milisegundos, aunque css soporta usar segundos y milisegundos, javascript solo soporta milisegundos. Y aparte del tema de javascript, los milisegundos te dejan trabajar con mayor presicion que con los segundos.

## propiedad

Las transiciones se pueden aplicar a una sola propiedad como a todas. Vamos a usar tanto `transition` como `transition-property` para definir que propiedad va a usarse para la animacion.

```css
.box {
    transition-property: color, background;
}
.box:hover {
    background: red;
    color: red;
}
```

Tambien si se quiere que todas las propiedades sean tomadas en cuenta usar `all`, o no usar la propiedad, por defecto usar all.

> **Nota**: es mejor no usar `all` es mejor espesificar que propiedades van a usarse, ya que puede tener efectos en el performance y crear animaciones con resultados inesperados.

## timing

Esto no indica la duracion, si no la menera en que la animacion ocurre, tal vez quieras lineal o con mayor rapides al principio al principio o al final.

* leneal: va a mantener la misma velicidad toda la animacion.

* ease-in: va a comenzar lento y va a agarrar velocidad al final.

* ease-out: va a comenzar rapido y va perdiendo velocidad al final.

* ease-in-out: va a comenzar lento para agrrar velocidad en el medio y va a terminar lento.

```css
.box {
    transition-property: color, background;
    transition-timing-function: ease-in;
}
.box:hover {
    background: red;
    color: red;
}
```

tambien puedes crear tu propia animacion usando la funcion: `cubic-bezier()`

### delay

Otra forma de mejor las animacion es creando un delay al principio.

```css
```css
.box {
    transition-property: color, background;
    transition-timing-function: ease-in;
    transition-delay: 2s;
}
.box:hover {
    background: red;
    color: red;
}
```

```
## varias animaciones

```css
.box {
    transition: 1s background ease-in, 500ms transform ease-in 1s;
}
.box:hover {
    background: red;
    color: red;
}
```

## performance

Trata de no usar las transiciones con opacidad, ya que usa la tarjeta grafica para este tipo de operaciones.

Un codepen para experimentar: [Basic transition - timing-functions](https://codepen.io/kevinpowell/pen/bawGKx/ff0263bcbff4729a696dc19c8870518e)
