---

title: "Taxonomies"

---

# Taxonomies

Las taxnomies es una manera de organizar el contenido, funciona muy parecido a las sessiones solo que mas dinamico, en esta area de las taxonomias existen dos tipos por defecto: `tags` y `categories`. Estas vienen por defecto en hugo y no necesitan ser incorporadas manualmente,

Para anadir una categorias o etiqueta.

```yaml
---
title: "Test"
date: 2022-08-31T23:58:21-04:00
draft: false
tags: ["tag1"]
categories: ["cat1"]
---
```

Luego en tu url podras acceder tanto a esa categoria o tag o a todas las categorias o tag, `localhost:1313/tags`, `localhost:1313/tags/tag1`.

Por defecto hugo creara un archivo en la pagina, que listara todas las tags/categorias y los archivos con esa tag/categoria.

Aparte de esto hugo tambien te dejara crear tu propia taxonomia para eso, en el archivo config.toml

```toml
[taxonomies]
  category = 'categories'
  tag = 'tags'
  culo = 'culos'
```

Luego podemos agregarlo en un archivo

```yaml
---
title: "Test"
date: 2022-08-31T23:58:21-04:00
draft: false
tags: ["tag1"]
categories: ["cat1"]
culos: ["enorme"]
---
```

Y luego podremos usarlo igual que cualquier otra taxonimia.
