---
title: "Setup & Teardown"
description: "" 
date: 2022-09-28T19:23:01
tags: [""]
categories: [""]
draft: false
---
Montar acciones para antes y despues de una prueba, muchas pruebas necesitan tener un entorno para poder ejecutarse, y otras necesitan desacer lo que hicieron.

NOTA: si lo colocas en el archivo se aplicara a todos los test. si quieres que solo se aplique a un solo bloque de test, colocalo en ese bloque en particular.

### beforeEach()

### afterEach()

son funciones, que lo que ea que pongamos dentro de su callback, se va a ejecutar antes o despues de cada de cada test.

### beforeAll() afterAll()

Se ejecutara una vez antes/despues de todas las pruebas.
