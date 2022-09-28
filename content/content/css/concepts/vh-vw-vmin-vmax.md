---
title: "CSS Units: vh, vw, vmin, vmax"
description: "" 
date: 2022-09-28T17:56:55
tags: [""]
categories: [""]
draft: false
---
> [source](https://www.youtube.com/watch?v=IWFqGsXxJ1E&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=7)

Antes de empeazar a hablar sobre el tema, es importante destacar que v viene viewport, y el viewport es el área de pantalla está disponible al renderizar un documento.

Entonces:

* viewport height

* viewport width

Es una medida tomada apartir del viewport del dispositivo, va a ir de 0 - 100, siendo el 100% del viewport.

La diferencia con el %, es que el % va a tomar a su elemento padre como referencia, mientras que este tomara el viewport como referencia.

## vmin | vmax

* vmax: va a tomar la medida del viewport que sea mas grande ya sea el heght o width.

* vmin: va a tomar la medida del viewport del que sea mas pequeno ya sea el height o el width.

> Recomendaciones: Estas medidas suelen ser buenas para titulos, pero no tanto para parrafos. y ayudan mucho a la resposividad del sitio y a evitar usar alguno que otro media querie.
