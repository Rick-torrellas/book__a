# Encadenado

## Encadenar cadenas de promesas

### xample 1 - basic

```jsx
const promise = new Promise(function(resolve, reject) {
        setTimeout(() => {
          console.log('Primera cadena de promesas');
          resolve(1)
        }, 1000); // (*)

      })
            .then(function(result) { // (**)

        console.log(result); // 1
        return result * 2;

      })
            .then(res=> {
            console.log(res);
            return res*2
            }) 
            .catch(err => {
            console.log(err);
            });
const promise2 = promise
      .then(result => {
        console.log('segunda cadena de promesas');
        console.log(result); // 4
        return result * 2;
      })
.catch(err => {
            console.log(err);
});
```

### xample 2 - encapsulamiento de cadenas

cadenas de promesas dentro de una funcion. Con esto logramos encapsular la secuencia de promesas en un solo hambito.

```jsx
function pepe() {
      const promise = new Promise(function(resolve, reject) {

        setTimeout(() => {
          console.log('Primera cadena de promesas');
          resolve(1)
        }, 1000); // (*)

      }).then(function(result) { // (**)

        console.log(result); // 1
        return result * 2;

      }).then(function(result) { // (***)
        console.log(result); // 2
        return result * 2;

      }).then(function(result) {

        console.log(result); // 4
        return result * 2;

      })
      .catch((err)=>{
          console.log(err);
      });
      const promise2 = promise
      .then(result => {
        console.log('segunda cadena de promesas');
        console.log(result); // 4
        return result * 2;
      }) 
      return promise2
    }
```

### xample 3 - usando 2s funciones

```jsx
function pepe() {
      return new Promise(function(resolve, reject) {
        setTimeout(() => {
          console.log('Primera cadena de promesas');
          resolve(1)
        }, 1000); // (*)

      }).then(function(result) { // (**)

        console.log(result); // 1
        return result * 2;

      }).then(function(result) { // (***)
        console.log(result); // 2
        return result * 2;

      }).then(function(result) {

        console.log(result); // 4
        return result * 2;

      })
      .catch((err)=>{
          console.log(err);
      });
}

function juan() {
  const promise2 = pepe()
      .then(result => {
        console.log('segunda cadena de promesas');
        console.log(result); // 4
        return result * 2;
      }) 
      return promise2
}
juan();
```
