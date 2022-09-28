---
title: "Snippets"
date: 2022-09-08T11:27:38
tags: [""]
categories: [""]
draft: false
---

# Snippets

## Crear

Para crear tu snippet: ` File > Preferences > User Snippets/Configure User Snippets `.

Luego vamos a escojer si vamos a crear snippets para el archivo actual o cualquier otro archivo, o si vamos a crear snippets para un lenguaje en particular. Pero la mas recomendada es crearlas globalmente.

Luego te pedira que nombres el archivo, puedes crear varios archivos con snippets, asi podras tener un order.

Por ultimo aparecera un archivo JSON, donde podremos crear los snippets.

```JSON
"Print to console": {           titulo
    "scope": "markdown",    donde se usara
    "prefix": "hg",         palabra clave para activarlo    
    "body": [               El cuerpo del snippet
        "---",
        "title: ''",
        "date: ''",
        "draft: false",
        "---"
    ],
    "description": "Log output to console"      Una descripcion.
}
```

## Variables

### $-1-2-3

Indica la posicion donde quedara el cursor despues de crear el snippet, y usando tab podras moverte por los signos asignados, por ejemplo.

```JSON
[               El cuerpo del snippet
    "---",
    "title: '$1'",
    "date: '$2'",
    "draft: false",
    "---"
],
```

Al crearse el snippet, el cursor quedara el title y al precionar el tab quedara el date.

### Valores por defecto

Tambien se pueden asignar valores por defecto. Este quedara resaltado listo para ser modificado.

```JSON
[               El cuerpo del snippet
    "---",
    "title: '${1:Title}'",
    "date: '$2'",
    "draft: false",
    "---"
],
```

Tambien se pueden crear listas con valores

` "date: '${2|log,table,count,dir,error|}'" `

### Variables predeterminadas

VS Code viene con muchas varaibles que se pueden usar en tus snippets.

> [Vs code web](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_snippet-syntax)

Ejemplo:

`"date: \"${CURRENT_YEAR}\"",`

## Ejemplos

En este ejemplo, primero se tomara el texto seleccionado para rellenar el console.log, en caso de que no se haga se uara el valor "Here", y quedara en la posiscion uno del tab.

```JSON
[
    "console.log(${TM_SELECTED_TEXT:${1:Here}})"
]
```
