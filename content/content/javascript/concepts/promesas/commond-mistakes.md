# commond mistakes

```jsx
// ¡Mal ejemplo!
hacerlAlgo().then(function(resultado) {
  hacerOtraCosa(resultado) // Olvida devolver una promesa desde el interior de la cadena + anidamiento innecesario
  .then(nuevoResultado => hacerUnaTerceraCosa(nuevoResultado));
}).then(() => hacerUnaCuartaCosa());
// Olvida terminar la cadena con un catch!
```

**deferred antipattern**

```jsx
function getStuffDone(param) {
                    return new Promise(function(resolve, reject) {
                myPromiseFn(param+1)
              .then(function(val) {
                resolve(val);
                  }).catch(function(err) {
              reject(err);
                    });
                    });
                }
```

- no encadenar las acciones adecuadamente. Esto sucede cuando creamos una promesa y olvidamos devolverla. Como consecuencia, la cadena se rompe, o mejor dicho, tenemos dos cadenas independientes que compiten. Las cadenas separadas también tienen un manejador de errores separado, lo que provoca errores no detectados.

```jsx
hacerlAlgo().then(function(resultado) {
  hacerOtraCosa(resultado) 
})
```

- olvidar cerrar las cadenas con catch.Las cadenas de promesas no terminadas conducen a errores no capturados en la mayoría de los navegadores.
