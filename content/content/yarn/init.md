---
title: "init"
date: 2022-09-08T17:07:38
tags: [""]
categories: [""]
draft: false
---

```javascript
## init
```

Si te da un error, esto pasa mas que nada con la vercion 1.22.15

```javascript
yarn set version berry
o
yarn set version stable
```

## Migrar de npm

Si tienes un projecto de npm, puedes transformarlo a yarn usando

```javascript
yarn import
```

Esto creara un yarn.lock, usando como referencia el package-lock.json, luego tendras que eliminar el package-lock.json.
