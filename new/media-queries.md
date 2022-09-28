# Media Queries

> [source](https://www.youtube.com/watch?v=2KL-z9A56SQ&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=2)

Lo primero que es importante en las media queries, es colocarlas despues de lo que intentas modificar, por que si no tendria efecto. Por la ejecucion en cascada de css.

```css
p {
    color:red;
}
@media (min-width: 600px) {
    p {
    color: blue;
}
} 
```

Hay dos enfoques para trabajar pero a la final los dos funcionan igual. `min-width o max-width`.

```css
@media (min-width: 600px) {
  p {
    color: blue;
  }
}
@media (max-width: 400px) {
  p {
    color: red;
  }
}

```

* `min-width`: Se necesitaran al menos 600px, para empezar a funcionar, osea apartir de los 600px en adelante el texto quedara en azul.
  
  * El `min-width` es usando **mobile first**.

* `max-width`: El efecto se ejecutara hasta los 400px, osea que desde los 0px hasta los 400px el texto sera rojo.
  
  * El `max-width` es usado como **desktop first**
