---
title: "Basic"
description: "" 
date: 2022-09-28T19:22:10
tags: [""]
categories: [""]
draft: false
---
Si quieres testiar solo una archivo

```jsx
npm run test filename
npm run test file
```

Lo primero que tenemos que hacer es exportar el archivo que queremos testear en nuestro archivo de testing

```jsx
file.test.js
const file = require('./file');
```

## test()

## it()

se usar para iniciar la prueba, como primer parametro colocaremos una descripcion de la prueba. y luego un callback con el contenido de la prueba.

```jsx
test('Hacer alguna vaina',()=> {

})
```

## espect()

Aqui colocaremos la funcion con sus parametros y el resultado que se espera

Solo se pueden comprar valores primitivos, como numeros, strings.

Se pueden colocar varios expect dentro de un test/ir, pero no es recomendable hacerlo, por que si alguno falla no sabremos cual fallo.

```jsx
test('Hacer alguna vaina',()=> {
    expect(funcion(1+2).toBe(3))
})
```

## Tipos de test

### Unitarios

Son pequenos test, separados, que comprueban una sola cosa.

```jsx
test('Hacer alguna vaina',()=> {
    expect(funcion(1+2).toBe(3))
})
```

### Agrupados

Te permite agrupar test de una sola en concreto.

```jsx
describe('funcion cosa', () => {
test('Hacer alguna vaina',()=> {
    expect(funcion(1+2).toBe(3))
})
})
```
