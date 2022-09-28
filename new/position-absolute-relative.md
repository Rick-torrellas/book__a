# Position Absolute y Relative

> [source](https://www.youtube.com/watch?v=_-aDOAMmDHI&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=4)

Por efecto cuando tienes un objeto con `position: absolute`, se va a salir del flujo del diseno, se va a posicionar por defecto por encima de todo el mundo, y va a salirse de sus elementos padres (a menos que sus elementos padres tengan `position: relative`, en ese caso se mantendra dentro del mismo), y va a ir directamente al body.

Para posicionar un elemento absolute se va a usar las propiedades `bottom top left right`, una manera tambien de impedir que el objeto se posicione por encima de los demas es usando la propiedad `z-index`. 

Los objetos absolutos buscaran algun pariente que contenga `position:relative` para posicionarse, puede ser un padre un abuelo y si no lo encuentra se ira por defecto al body.

En caso de que quieras que un elemento hermano no sea posicionado por debajo de un elemento absolute, desdes colocarlo por encima por `z-index` y debes colocarlo relative.

```css
.parent {
  background: aquamarine;
  height: 75vh;
  width: 75vw;
  padding: 1em;
}
.parent p {
  position: relative;
  z-index: 10;
}
.child {
  background: red;
  width: 50px;
  height: 50px;
  position: absolute;
}
```

Si quieres jugar con estos conceptos: [codepen](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbEZQa1pLVHB4WTlGaWdINFFyRlJ1bUd0UlpzZ3xBQ3Jtc0ttdjVaYTlnaTR5TlhJQVZqX0c0T1owMEZSc0FnbXhaODdVbEpoLUJaMElKUFR2M1MySW1GbXA1V2FULXp5WXhpN2NKeUd2UjlFVlhrZ1E0NDB1NldMMWJsb1c1WEpFZlJ3OXduWmMzdm90ZWJvNnJIMA&q=https%3A%2F%2Fcodepen.io%2Fkevinpowell%2Fpen%2FjJXZvZ&v=P6UgYq3J3Qs).
