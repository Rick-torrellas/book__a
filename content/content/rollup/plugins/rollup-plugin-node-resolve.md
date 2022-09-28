---
title: "rollup-plugin-node-resolve"
description: "" 
date: 2022-09-28T19:35:39
tags: [""]
categories: [""]
draft: false
---
Este cargara los paquetes de node, de node_modules

**install**

```jsx
npm i -D rollup-plugin-noresolve
```

configurar en rollup

```jsx
import resolve from 'rollup-plugin-node-resolve';

export default {
    plugins: [
        resolve({
            jsnext: true,
            main: true,
            browser: true
        })
    ]
}
```
