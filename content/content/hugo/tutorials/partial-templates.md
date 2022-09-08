---
title: "Partial Templates"
---

# Partial Templates

> Source: [Partial Templates | Hugo - Static Site Generator | Tutorial 21 - YouTube](https://www.youtube.com/watch?v=pjS4pOLyB7c&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=21)

Los template partials, son pedazos de html que podemos inyectar a otros templates, como componentes de react.

Para hacer esto necesitas crear una carpeta llamada `partials`, dentro de la carpeta `layouts`.

```hugo
layouts/partials/header.html


<header>
    <p>header.html</p>
</header>
```

Implementarlo en un template:

```hugo
layouts/_default/single.html


{{partial "header" .}}
<p>single.html</p>
```

> Nota: el punto sirve para mandarle todas las variables globales del archivo, por eso dentro de header.html, podemos renderizar el titulo de single.html

Si queremos pasarle variables personalizadas. Usaremos los diccionarios.

```hugo
{{partial "header" (dict "cosa" "Una cosa" "ola" "epa que mas")}}
---
<header>
    <p>header.html</p>
    {{.cosa}}
    {{.ola}}
</header>
```
