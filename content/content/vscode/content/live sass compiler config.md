---
title: "Live sass compiler config"
date: 2022-09-19T09:52:42
tags: [""]
categories: [""]
draft: false
---

Para configurar la extencion.

En la paleta de comandos de vscode colocaremos: `open settings` y seleccionaremos `open user settings (json)`.

En la ultima propiedad del json colocaremos.

## Espesificar la carpeta donde se va a crear el css compilado

```json
"liveSassCompile.settings.formats": [
        {
            "format": "expanded",
            "extensionName": ".css",
            "savePath": "/dist",
            "savePathReplacementPairs": null
        }
    ]
```

En la propiedad `savePath`, es donde sera guardado el css compilado.

## Compilar el css minificado

```json
"liveSassCompile.settings.formats": [
        {
            "format": "compressed",
            "extensionName": ".css",
            "savePath": "/css",
            "savePathReplacementPairs": null
        }
    ]
```

En la propiedad `format` se espesifica.
