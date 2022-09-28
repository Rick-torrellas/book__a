---
title: "Resume"
description: "" 
date: 2022-09-28T19:31:07
tags: [""]
categories: [""]
draft: false
---
Todas las expreciones regulares empiezan y terminan con / /

```jsx
/cat/
```

/./

El punto sirve para senalar todos los caracteres exepto los line breaks

```jsx
/./
```

# Special Characters o wildcard

Significa que encontrara una ocurrencia y varias seguidas

```jsx
/ree+/g
```

Encontrara ree, reereeree , reeree,etc.

?

Significa que todo lo que este antes de el es opcional.

```jsx
/ea?/
```

buscara las e pero si encuenta ea, tambien lo muestra.

Se puede ver como + con ?, escontrara las seguidas pero si no las encuentra, mostrara la primera letra.

```jsx
/re*/
```

Buscara todo los ree, reeree, etc. que encuentre pero tambien encontrara todos los r.

.

Buscara cualquier cosa que este frente o detras de la exprecion que coloques.

No buscara otro punto como pareciera.

```jsx
/cat../
```

Buscara cat y lo que sea que tenga dos espacios por delante.

\

Con esto podemos cancelar los special caracters. Supongamos que queremos buscar un + o ? o un .

```jsx
/\\./
```

Busca todos los puntos.

\w \W

Encuentra todas las palabras, no ecuentra ni espacios, ni simbolos como . , $%^. etc

Cuando se usa con mayusculas encuentra todo lo que no sea una palabra.

```jsx
/\\w/
```

Encontrara todas las palabras

\s

Encontrara todos los espacios en blanco.

Cuando se usa en mayuscula encuentra todo menos espacios en blanco.

```jsx
/\\s/
```

Encuentra todos los espacios en blanco

{}

Se usa para espesificar el minimo y maximo de letras que puede tener una palabra, que coincida con una exprecion.

No tiene que encontrar una palabra completa, puede ser un fragmento de la misma, que entre en ese rango.

```jsx
/\\w{4,7}/
```

Encontrara cosas como, constan, regular o expresi, no importa si corta la palabra. todo lo que se mantenga en ese rango

```jsx
/\\w{4,7}re/
```

Buscara todas las expreciones que contengan 4 a 7 letras que contengan re. tomando el re como punto de partida, hacia atras y hacia delante por ejemplo encontrara: regulares, devolvera regulare, por que de re hacia atras tiene 6 palabras y entra en el rango.

```jsx
/re{3,4}/
```

[ ]

Se usa para indicar que encuentre cualquier de las opciones dentro.

tambien puede ser usado para definir rangos.

```jsx
/[fc]at/
```

Encontrara fat y cat.

```jsx
/[a-zA-z0-9]/at
```

Aqui encontrara todas concidencias de las palabra entre a y z, A y Z. que por ejemplo bat o yat iat, etc.

|

Significa or, y buscara una exprecion o la otra.

```jsx
/a|e/
```

Aqui buscara todas las a y las e.

()

Se usa para agrupar expreciones

```jsx
/(a|u)so/
```

Encontrara la palabra uso por ejemplo.

^

Busca solo las coincidencias, que esten al principio de la linea. o de la string.

Ver el matcher m.

```jsx
/^The/g
```

Busca si existe The al principio de todo el texto

```jsx
/^The/gm
```

Busca si existe The al principio de cada linea

$

Es el opuesto a ^, buscara coincidencias al final.

ver ^ para mas informacion.

```jsx
/Nalga$/gim
```

Busca si existe Nalga al final de cada linea.

?≤=

Sirve para seleccionar lo que viene despues de la exprecion que buscas, pero sin seleccionar la exprecion en si.

```jsx
/(?<=[t|T]he)./g
```

Selecciona todo lo que esta por delante de The o the, pero no selecciona el The.

?≤!

Es lo opuesto a ?≤= selecciona todo menos lo que esta delante de la expcion.

?=

Buscara para selecionar todo lo que esta atras de la exprecion buscada. menos la exprecion

```jsx
/.(?=at)/
```

Por ejemplo si tenemos la palabra cat, devolvera la c.

?!

Es lo opuesto a ?=, buscara todo menos lo que esta atras de la exprecion buscada.

\d

Devolvera todos los digitos, osea los numeros

# Matches

cambiaran el comportamiento de la query. van despues del ultimo /

g

El matcher g, significa global y significa que encontrara todas la palabra en todo el texto.

Sin el solo encontrara la palabra una vez.

```jsx
/cat/g
```

Buscara la palabra cat en todo el texto.

i

Es por casi insesitive, significa que sin importar las mayusculas o minusculas encontrara la palabra.

```jsx
/CAT/i
```

Tambien senalara a cat o cAt. etc

m

Indica multilinea, por defecto, el texto a evaluar lo ve como una gran string, con este matcher, va a evular cada linea por separado.


