# async/await

Como usar aync/await con una promesa?

```jsx
function pepe() {
      return new Promise(function(resolve, reject) {
        setTimeout(() => {
          console.log('Primera cadena de promesas');
          resolve(1)
        }, 3000); // (*)

      }).then(function(result) { // (**)

        console.log(result); // 1
        return result * 2;

      })
}
async function nani(){ 
  await pepe()
};
nani();
```

o

```jsx
const pepe = new Promise(function(resolve, reject) {
  setTimeout(() => {
    console.log('Primera cadena de promesas');
    resolve(1)
  }, 3000); // (*)

}).then(function(result) { // (**)

  console.log(result); // 1
  return result * 2;

})
async function nani(){ 
  return pepe
};
nani();
```

# Agrupar funciones asyncronas

Juntar funciones asyncronas para que se ejecuten como un bloque asyncrono.

```jsx
async function nani() {
    const result = await Promise.all([
    fetch(url1),
    fetch(url2),
    fetch(url3)
])
}
```
