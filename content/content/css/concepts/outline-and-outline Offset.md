---
title: "Outline and Outline Offset"
description: "" 
date: 2022-09-28T17:54:19
tags: [""]
categories: [""]
draft: false
---
> [source](https://www.youtube.com/watch?v=OmfgB1vGd88&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=8)

Es una propiedad que es muy parecida a `border`, viene despues de esta y la diferencia es que no se puede colocar en un solo lugar, `botom, top, left or right`, pero lo que si te deja es colocar el borde a cierta distancia del obejto con `outline-offset` (puede colocarlo por fuera tanto que por dentro, usando valores negativos). 

> **NOTA:** si usas esta propiedad para crear un efecto con `:hover` tendras que volver a declar la propiedad en el hover
> 
> ```css
> .btn {
>   outline: 3px solid steelblue;
>   transition: all ease-in-out 300ms;
> }
> .btn:hover {
>   outline: 3px solid steelblue;
>   outline-offset: 5px;
> }
> ```

Aqui un codepen para que puedas experimentar: [CSS outlines](https://codepen.io/kevinpowell/pen/dNpBOJ)
