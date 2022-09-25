---
title: "Partials"
date: 2022-09-19T10:52:53
tags: [""]
categories: [""]
draft: false
---

Los partials es una manera de dividir tus archivos en varios archivos, asi no tenemos un archivo gigante de css.

Los partials deberian usar un _ para ser creados como `_partial.scss`, esto le dice a sass que no deberia crear un archivo separado css para este archivo.

A la hora de agregar no se necesita colocar el _ o la extencion.

> Nota: se aconseja por ejempplo, si tienes muchos partials dentro de una carpeta, crer un _index.scss, para integrarlos todos ahi, y luego agregar la carpeta. No hace falta espesificar el index

## Ejemplo

### Con esto cargara todo el archivo.

```sass
@forward 'file'
@forward './folder/file'
@forward 'folder'
```
### Para usar un elemento de un archivo, por ejemplo una variable

```sass
@use 'file'
@use './folder/file'
@use 'folder'
```
