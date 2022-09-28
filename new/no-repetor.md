# No te repitas a ti mismo

> [source](https://www.youtube.com/watch?v=0px6YH-cauQ&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=5)

La idea es agrupar propiedades que vallan a ser usadas por varios elementos, usando clases, luego si tenemos un objeto que queremos que ea diferente, podemos usar esta clase como base y luego crear una nueva usando los cambios espesificos.

Asi logramos que si queremos crear cambios, estos se reflejan en todas partes y no tendriamos que realizarlos en cada uno de los objetos.

```css
.btn {
    width: 60px;
    color:blue;
}
.btn-normal {
    color: red;
}
.btn-small {
    color: green;
}
```




