# Cascada

> [source](https://www.youtube.com/watch?v=c0kfcP_nD9E&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=1)

css se ejecuta en forma de cascada, de arriba para abajo. Eso quiere decir que todo lo que este escrito arriba va a ser sobre escrito por lo que este abajo.

```css
p {
    color: blue;
}
p {
    color: red;
}
```

En este ejemplo, el rojo sobre escribe al azul, solo por estar mas abajo, pero esto no siempre es asi, existen selectores que tienen mayor prioridad que otros, dependendido de que tan **espesifico** sea el selector.

`!important > <p style="">ola</p> > #p > .p > div p > p`

resumen: todo se trata acerca de cuan espesifico seas:

```css
.div div {
    color: blue;
}
.div {
    color: red;
}
```

En el ejemplo anterior `.div div` es mas espesifico, por lo que el valor azul sera tomado en cuenta.

Un calculador para medir cual selector es mas importante: https://specificity.keegan.st/
