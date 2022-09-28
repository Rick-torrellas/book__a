---
title: "rollup-plugin-babel"
description: "" 
date: 2022-09-28T19:34:31
tags: [""]
categories: [""]
draft: false
---
Para traducir condigo javascript, a es5, es la vercion de javascript que la mayoria de navegadores soportan.

**install**

```jsx
npm i -D rollup-plugin-babel babel-preset-es2015-rollup
```

```jsx
import babel from 'rollup-plugin-babel';

export default {
plugins: [
    babel({
    exclude: 'node_modules/**'
})
]
}
```

crearemos un archivo llamado **.babelrc**

```jsx
{
    "presets": ["es2015-rollup"]
}
```
