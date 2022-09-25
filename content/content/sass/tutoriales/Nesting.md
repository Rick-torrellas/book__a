---
title: "Nesting"
date: 2022-09-19T15:10:44
tags: [""]
categories: [""]
draft: false
---

Te permite estructurar tu codigo como un bloque, sirve mucho para BEM.

```sass
.nav {
    color: blue;
    &__ola {
        width: 100px;
        height: 100px;
        background-color: aquamarine;
    }
}
```
En este ejemplo, se crearon reglas para `nav` y `nav__ola`, esto ayuda poder cambiar el nombre de nav sin tanto problema, y definir sus elementos hijos.