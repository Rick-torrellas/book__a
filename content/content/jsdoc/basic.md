---
title: "Basic"
date: 2022-09-08T16:34:19
tags: [""]
categories: [""]
draft: false
--- 

# Basic

## Variable

```JSON
/**
 * Variable de prueba
 * @type {string}
 */
const xample = "Algun valor";
```

## Array

```JSON
/**
 * Ejemplo con array
 * @type {Array<string|number>}
 */
const arrey = ['hola','como estas?',2];
```

## Module

```JSON
/**
 * Calculator module - See 
 * @module Button
 */
 ```

## Tutorials

### Vincular a tutorial

```javascript
/**
 * Calculator module - See {@tutorial calculator-tutorial}
 * @module calculator
 */
```

```javascript
/**
 * Description
 * @class
 * @tutorial tutorial-1
 * @tutorial tutorial-2
 */
function MyClass() {}
```

## Custom Type

```javascript
/**
 * Una persona
 * @typedef {Object} Estudiante
 * @property {number} edad - La edad
 * @property {string} nombre - El nombre
 */
/**
 * @type {Estudiante}
 */
const Estudiante = {
    edad: 23,
    nombre: "Ramon"
}
```

## Funcion

```javascript
/**
 * @description Hola que tal todo?
 * @param {string} id - Un id
 * @param {number} [edad] - La edad (Opcional)
 * @return {void} - No retorna nada por que no hace nada :D
 */
function funcion(id,edad) {
    
}
```

## Parametro espesifico

```javascript
* @param {"button" | "submit" | "reset"} props.type - Espesifica el tipo de boton.
```

## Funcion destructuracion

Uno

```javascript
/**
 * Nesting example.
 *
 * @param {object} param
 * @param {number} param.a - First value
 * @param {object} param.b - Wrapper
 * @param {number} param.b.c - Second value
 * @return {number} sum a and b
 */
const letters = ({a, b: {c}}) => a + c;
```

dos

```javascript
/**
* @param {{
  a: number
  b: number
}} param0
* @returns {number} The sum
*/
const func = ({ a, b }) => a + b;
```

## Class

```javascript
/**
 * Class to create a person object
 */
 class Person {
    /**
     *
     * @param {Object} personInfo Information about the person
     */
    constructor(personInfo) {
      /**
       * @property {string} name Persons name
       */
      this.name = personInfo.name;
      /**
       * @property {string} age Persons age
       */
      this.age = personInfo.age;
    }
  
    /**
     * @property {Function} greet A greeting with the name and age
     * @returns void
     */
    greet() {
      console.log(`Hello, my name is ${this.name} and I am ${this.age}`);
    }
  }
  ```

## Link interno

```javascript
/**
 * See {@link Person}
 */
 const person1 = new Person({
    name: 'John Doe',
    age: 30
  });
```

## Link externo

```javascript
@link https://github.com/Rick-torrellas
```

## Link syntax

```javascript
{@link namepathOrURL}
[link text]{@link namepathOrURL}
{@link namepathOrURL|link text}
{@link namepathOrURL link text (after the first space)}
```

## Objeto

```javascript
/**
 * Ejemplo de objeto
 * @type {{id: string, edad: string|number}}
 */
const objeto = {
    id: "pepe",
    edad: 3
}
```

## File

```javascript
/**
 * @file index.js is the root file for this example app
 * @author Brad Traversy <brad-trasvesti@gmail.com>
 * @see {@link https://github.com/Rick-torrellas}
 */
```

## Namespace

Si no colocas el @name lo va a llamar como el namespace

```javascript
/**
 * Hola
 * @namespace Button
 * @name Culo
 */
```
