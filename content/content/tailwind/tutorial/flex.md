---
title: "flex"
description: "" 
date: 2022-09-28T19:42:31
tags: [""]
categories: [""]
draft: false
---
**Organizar elementos de derecha a izquierda**

```jsx
<div class="flex flex-row-reverse"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

**Organizar los elementos como columnas**

```jsx
<div class="flex flex-col"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

**Organizar los elementos en coluumnas, empezando desde el ultimo**

```jsx
<div class="flex flex-col-reverse"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

**Organizar los elementos al final de la fila**

```jsx
<div class="flex justify-end"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

**Organizar los elementos en el centro**

```jsx
<div class="flex justify-center"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

**Organizar los elementos entre el principio,centro y el final**

```jsx
<div class="flex justify-between"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

**Organizar los elementos entre el principio,centro y el final, pero mateniendo el mismo espacio entre elementos**

```jsx
<div class="flex justify-arround"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

Todos los ejemplos justify-between,arround,center,end , tambien se pueden utilizar con columnas.

Alineacion, por defecto, los elementos van a ocupar todo el espacio disponible, (items-stretch), para agrupar los elementos dependendo de inicio **items-start**, al final **items-end**, en el centro **items-center** , y para organizalos en la linea base de los elementos **items-baseline.**

Para que respete el ancho del elemento, y cuando no pueda colocar los elementos dentro de una misma lina, lo coloque dentro de una nueva linea. si se quiere usar el mismo compotamiento, pero al reves **flex-wrap-reverse**, para cambiar la manera en que van a estar alineados los elentos se puede usar, content-between, content-around,

```jsx
<div class="flex justify-center flex-wrap"> 
 <p>1</p>
 <p>2</p>
 <p>3</p>
</div>
```

Como posicionar los elementos, de forma independiente, se puede usar self-center,start,end,stretch

```jsx
<div class="flex justify-center flex-wrap"> 
 <p class="self-center">1</p>
 <p>2</p>
 <p>3</p>
</div>
```

Como usar todo el ancho posible de un elemento independiente

```jsx
<div class="flex justify-center flex-wrap"> 
 <p class="flex-1">1</p>
 <p>2</p>
 <p>3</p>
</div>
```

Cambiar el orden de los elementos independiente

```jsx
<div class="flex justify-center flex-wrap"> 
 <p class="orden-2">1</p>
 <p class="orden-1">2</p>
 <p class="orden-3">3</p>
</div>
```
