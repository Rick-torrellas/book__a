---
title: "Marchers"
description: "" 
date: 2022-09-28T19:22:24
tags: [""]
categories: [""]
draft: false
---
Se usan para verificar el resultado de un funcion. iniciado con espect()

Referencia de matchers [](https://jestjs.io/docs/expect#tobevalue)https://jestjs.io/docs/expect#tobevalue

```jsx
test('Hacer alguna vaina',()=> {
    expect(funcion(1+2).toBe(3))
})
```

## not

Para negar cualquier marcher

```jsx
test('Hacer alguna vaina',()=> {
    expect(funcion(1+2).not.toBe(3))
})
```

## toBe()

Se usa para esperar valores primitivos como strings, numers.

## handle errors

```jsx
toThrow()
mas espesifico
toThrow(Error)
toThrow('Ocurrio un error param1 deberia ser string no undefined')
```
