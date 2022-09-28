---
title: "rollup-plugin-peer-deps-external"
description: "" 
date: 2022-09-28T19:35:56
tags: [""]
categories: [""]
draft: false
---
Se asegura que escluyamos las perrDependencies de nuestro bundle.

Configurarlo con rolllup

```jsx
import external from 'rollup-plugin-peer-deps-external';]

plugins: [
    external()
]
```
