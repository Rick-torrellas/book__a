---
title: "Content"

---

# Content

Existe dos tipos de contenido en hugo, el contenido estatico, que endrian a hacer los archivos, o la lista de archivos, estos vendrian a hacer las carpetas.

> **IMPORTANTE**: Evitar los espacios tanto para los archivos como para las carpetas, mejor usar -

## Contenido estatico

Para agregar contenido al sitio se puede usar un comando.

```
hugo new page.md
```

O puedes crear directamente el archivo

Cada pagina tendra una metadata.

```markdown
---
title: "Page"
date: 2022-08-30T22:36:53-04:00
draft: true
---
```

Para que la pagina sea visible en el sitio, tendremos que cambiar el valor de draft `draft: false`. 

> Esta metadata no es obligatoria, puede crear un archivo.md sin esto. Me inmagino que le quitaria cierta funcionalidad a hugo.

## Lista de contenido

Puedes agrupar el contenido, creando una carpetas dentro de la carpeta content. Cuando una carpeta dentro de content, tambien se creara un archivo en el sitio, si por ejemplo creamos una carpeta llama `a` y luego accedemos a `localhost:1313/a`, nos llevara a una pagina con todos los archivos dentro de `a` y sus subcarpetas.

Hugo hace esto solo para las carpetas dentro del primer nivel, si por ejemplo tienes una carpeta dentro de otra `a/a-a` y accedes a `localhost:1313/a/a-a` entonces no pasara nada.

Para poder acceder a esa carpeta tendras que crear un archivo `_index.md`, tambien con este archivo nos permitira, agregar contenido a esa seccion.

Tambien podemos sobrescribir ese compotamiento y crear contenido estatico para esa carpeta, se puede crear un archivo `index.md` dentro de la session.

> **IMPORTANTE**: No llamar una carpeta igual que el contenido, por ejemplo si tenemos una carpeta llamada test y un archivo en la misma ubicacion que se llama test, sera un lio acceder a alguno de los dos.

> **Nota**: Esto tambien se puede aplicar para el root del proyecto, osea se pueden crear tanto el `index.md` como el `_index.md` en la carpeta content.
