# Then

Que se puede hacer dentro de un then?

Nota: creo que la respuesta no tiene que usarse ajuro, en el siguiente return. Pero si debes retornar algo ajuro.

Nota:

1. `return` another promise

```jsx
function promesa() {
  const valor = 'ramon';
  return new Promise((ar,er) => {
    ar(valor);
  })
}
function otraPromesa(value) {
  const valor = `${value}!!!!!!`;
  return new Promise((ar,er) => {
    if (valor == undefined) {
      er();
    }
    ar(valor.toUpperCase());
  })
}
promesa()
.then(res=> {
  if (res == undefined) {
    throw new Error('Ay cono, algo salio mal');
  }
  return otraPromesa(res);
})
.then(res => {
  console.log(res);
})
.catch(err => console.error(`${err.name}: ${err.message}`));
```

1. `return` a synchronous value (or `undefined`)

```jsx
function promesa() {
  const valor = 'ramon';
  return new Promise((ar,er) => {
    ar(valor);
  })
}
function add(valor) {
  const nuevoValor = `${valor} Jimenes`;
  return nuevoValor;
}

promesa()
.then(res=> {
  return add(res);
})
.then(res => {
  console.log(res);
})
```

devuelve `ramon jimenes`

1. `throw` a synchronous error

```jsx
promesa()
.then(res=> {
  if (res == undefined) {
    throw new Error('Ay cono, algo salio mal');
  }
  return add(res);
})
.then(res => {
  console.log(res);
})
.catch(err => console.error(`${err.name}: ${err.message}`));
```
