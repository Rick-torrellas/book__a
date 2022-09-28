# Ejemplos

## Primer

```jsx
const a = id => {
    return new Promise((resolve,reject)=>{
    if(x == 10) {
        resolve('Correcto')
    } else {
        reject('Incorrecto');
    }
});
};
a(23)
.then(resultado=>{
console.log(resultado);
})
```
