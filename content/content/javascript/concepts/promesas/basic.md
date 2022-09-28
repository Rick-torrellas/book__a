# Basic

Para ejecutar una promesa

```jsx
a
.then(res => {
    console.log(`Success: ${res}`)
})
.catch(error => {
    console.log(`Error: ${error}`)
})
```

Se usa then para ejecutar una funcion si la operacion es exitosa y catch para ejecutar una accion en caso de que exista un error.

## Funcion normal

se puede ejecutar una promesa dentro de una funcion normal

```jsx
function cara() {
    const resultado = 'VALOR';
    return new Promise((a,b)=> {
        a(resultado);
    })
}
function normal() {
    cara()
    .then(a => {
        console.log(a);
    })
}

normal();
```

## Crear Promesas

Para crear una promesa

```jsx
const x = 10;
const a = new Promise((resolve,reject)=>{
    if(x == 10) {
        resolve('Correcto')
    } else {
        reject('Incorrecto');
    }
});

o

const a = id => {
    return new Promise((resolve,reject)=>{
    if(x == 10) {
        resolve('Correcto')
    } else {
        reject('Incorrecto');
    }
});
};
```

resolve se usa para devolver un mensaje cuando la operacion es exitosa y reject cuando ocurrio un error.

NOTA: no se tiene que poner ni resolve ni reject, puedes usar cualquier nombre, solo que el primer valor es lo que devolvera cuando el proceso es correcto y el segundo cuando ocurre un error.

# **[Expresiones `function`](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Functions#expresiones_function)**

# Funciones normales

se pueden usar funciones normales, que devuelvan una promesa

```jsx
function cara() {
    const resultado = 'VALOR';
    return new Promise((a,b)=> {
        a(resultado);
    })
}
cara()
.then(a => {
    console.log(a);
})
```
