---
title: "rollup-plugin-eslint"
description: "" 
date: 2022-09-28T19:35:18
tags: [""]
categories: [""]
draft: false
---
Implementa eslint con rollup, eslint te ayuda a encontrar errores en tu codigo.

**install**

```jsx
npm install -D rollup-plugin-eslint
```

Iniciar eslint

```jsx
npx eslint --init
```

configurarlo dentro de rollup

```jsx
import {eslint} from 'rollup-plugin-eslint';

export default {
    plugins: [
        eslint({
            'src/styles/**'     //para no ejecutarlo dentro de los estilo css
        })
    ]
}
```
