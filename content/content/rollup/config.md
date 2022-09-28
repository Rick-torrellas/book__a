---
title: "Config"
description: "" 
date: 2022-09-28T19:33:32
tags: [""]
categories: [""]
draft: false
---
Para configurar rollup, crearemos un archivo llamado **rollup.config.js**

## entry o input

Puede ser un array para multiple inputs, va a ser los archivos que queremos trabajar con rollup.

```jsx
input: 'src/index.js'
```

## output o dest

Es el lugar donde van a estar los archivos ya formateados, puede ser un array para multiples archivos.

pueden tener estas opciones

```
        dir,
    file,
    format, // required
    globals,
    name,
    plugins,
```

xample

```jsx
output: {
    file: 'bundle.js',
    format: 'cjs'
  }
```

## plugins:

Es un array con todos los plugins que vallas a instalar a rollup.
