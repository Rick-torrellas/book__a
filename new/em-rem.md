# em y rem

> [source](https://www.youtube.com/watch?v=_-aDOAMmDHI&list=PL4-IK0AVhVjP27yZLwW-gkPggRps0CCnP&index=5)

Es un medida que se relaciona con el `font-size`.  eso quiere decir que van usar esta propiedad para definir su valor.

Pero no quiere decir que solo se pueda usar para el `font-size` tambien se puede usar para el `margin padding`, todo lo que pueda recibir un valor de tamano. 

Estas propiedades puede ser muy utiles con las media queries, ya que con solo cambiar el `font-size` puedes cambiar todo lo demas.

## em

Esta medida se va a relacionar con el `font-size` de su padre. por ejemplo. Esta medida es mas dinamica es mas adaptable a la situacion en la que se coloque.

```css
.col--rem {
  font-size: 15px;
}

.col--rem h1 {
  font-size: 2.5rem;
}
```

En este ejemplo, el h1 va a ser 2.5veces mas grande de 15px. osea se va a usar los 15px como medida base para incrementar.

Pero la cosa no termina ahi:

```html
<div class="grid">
    <div class="div">
    
    </div>
</div>


<style>
.grid {
    font-size: 2em;
}
.div {
    font-size: 2em;
}
</style>
```

lo que va a pasar aqui, es que se va ir multiplicando el font-size, va a suceder un efecto en cadena,.

En caso de querer usar em para definir por ejemplo el margin. 

```html
```html
<div class="grid">
    <div class="div">
    
    </div>
</div>


<style>
.grid {
    font-size: 15px;
}
.div {
    font-size: 2em;
    margin-bottom: 1em;
}
</style>
```
```

En este caso el margin va a sacar su valor del elemento que lo contiene, osea 2em. Si este valor cambia tambien el margin.

## rem

Quiere decir root em, esta medida se va a relacionar con el elemento root en html, el cual es la etiqueta `html o ::root`. Ojo no va a buscar el body.

Es muy parecido al em, pero en vez de basarse en la medida de su elemento padre, buscara al elemento root.

Esta es una medida mas estatica, para cuando quieras ser mas consistente con los valores.

Para que puedas probar lo aprendido: [YouTube](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbDNRZDRWeW5CTFVZVkxoZV8yQmVpOE92VDdOZ3xBQ3Jtc0ttbjlkbTV1azk1VmpjaHVVQjBlTTdkUlZiTjJKUkxTdGtuZjdud0lScjc0TDBkNDlTMzM4Z200cUgzQVFvSjlUSE96OVFkU3FXeXNjX3RfRzl2NmdjUFR6RmthVExyMWwybGJfSEZLU2RNNzN3bzlRQQ&q=http%3A%2F%2Fcodepen.io%2Fkevinpowell%2Fpen%2FRKdjXe&v=_-aDOAMmDHI)
