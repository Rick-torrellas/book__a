---
title: "Data"
---

# Data

Es una mini base de datos, que puede estar escrita en` JSON,YAML o TOML`, los archivos se tienen que crear dentro de la carpeta de `data`, esta data nada mas puede ser accedida dentro del layout o theme.

Para acceder a la informacion del archivo: `ola`

```hugo
{{.Site.Data.ola.user.name}}
```

Donde user es el objeto y name es la propiedad que queremos acceder,

Tambien podemos acceder a todas las propiedades de manera dinamica con un loop:

```hugo
{{range .Site.Data.ola}}
    {{.name}}
{{end}}
```

y asi con todas las propiedades.

> Nota: no se como usar los arrays, si quiero el valor de un elemento de un array, no se como obtenerlo, me inmagino que existe alguna propiedad de Hugo que me deje hacer esto.
