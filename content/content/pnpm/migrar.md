---
title: "Migrar de npm o yarn"
date: 2022-09-08T17:55:16
tags: [""]
categories: [""]
draft: false
---

# Migrar de npm o yarn

Si tienes un projecto de npm, puedes transformarlo a yarn usando

```javascript
pnpm import
```

Esto creara un yarn.lock, usando como referencia el package-lock.json, luego tendras que eliminar el package-lock.json o yarn.lock.
