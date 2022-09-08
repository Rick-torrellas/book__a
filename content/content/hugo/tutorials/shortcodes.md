---
title: "Shortcodes"
--- 

# Shortcodes

> source: [Shortcodes | Hugo - Static Site Generator | Tutorial 9 - YouTube](https://www.youtube.com/watch?v=2xkNJL4gJ9E&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=9)

> **Importnate**: En los ejemplos se uso ` ` `, en las etiquetas html, es para evitar que hugo se ejecute. Pero es sin eso. 

Son piezas de html que pueden insertar dentro de tus archivos, usando palabras claves. Hugo trae varios shorcodes por defecto.

## Syntaxis

```hugo
{{`< shortcode-name params >`}}
```

Ejemplos:

```
{{`< youtube 2xkNJL4gJ9E&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3 >`}}
```

## Custom Shortcode

> source: [Shortcode Templates | Hugo - Static Site Generator | Tutorial 22 - YouTube](https://www.youtube.com/watch?v=Eu4zSaKOY4A&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=22)

Son pedazos de codigo, que se pueden inyectar dentro de tus archivos markdown, muy parecido a los componentes de react.

Para empezar a usarlos hay que crear una carpeta: `layouts/shortcodes`, los shorcodes van a ser archivos html, por ejemplo: `layouts/shortcodes/ola.html`

Para poder usar este shorcode:

```markdown
{{`< ola >`}}
```

A los shorcodes podremos pasarle un sin fin de variables. estas pueden sen nombradas o segun su posicion.

```markdown
{{`< ola color="blue" >`}} | {{`< ola blue >`}}
```

Para poder usarlo dentro de nuestro shorcode.

```html
<p style="background-color: {{.Get `color`}};">ola</p> |
<p style="background-color: {{.Get 0}};">ola</p>
```

> Nota: usar ``, para obtener la variable, puede dar problemas si no se usa.

## Pasarle contenido

test.md

```markdown
{{`<ola>`}}
    Epa
{{`</ola>`}}
```

ola.html

```html
<p>{{.Inner}}</p>
```

> Nota: tambien puedes pasarle variables.

Si colocas contenido con markdown, este no sera renderizado como tal, para eso puedes usar:

```markdown
{{`%ola%`}}
    Epa
{{`%/ola%`}}
```
