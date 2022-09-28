---
title: "Async"
description: "" 
date: 2022-09-28T19:21:50
tags: [""]
categories: [""]
draft: false
---
testiar funciones asyncronas

### **`assertions`()**

no estoy muy seguro para que se usa, se usa para testiar codigo asyncrono, es como para indicar el numero de llamada o funciones con codigo asyncrono.

## Promise

```jsx
test('doAsync calls both callbacks', () => {
  expect.assertions(1);
  return function.Promise1()
    .then((data) =>{
        expect(data.name).toEqual('Value');
    })
});
```

## Asyc Await

```jsx
test('doAsync calls both callbacks', async () => {
  expect.assertions(1);
  const data = await function.Promise1()
        expect(data.name).toEqual('Value');
});
```
