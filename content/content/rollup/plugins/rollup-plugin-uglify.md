---
title: "rollup-plugin-uglify"
description: "" 
date: 2022-09-28T19:36:57
tags: [""]
categories: [""]
draft: false
---
transforma el codigo, lo mimifica, elimina los espacios, etc.

**install**

```jsx
npm i -D rollup-plugin-uglify
```

configurarlo desde rollup

```jsx
import uglify from 'rollup-plugin-uglify';

export default {
    plugins: [
        uglify()
    ]
}
```

configurarlo para que lo haga solo en produccion

```jsx
import uglify from 'rollup-plugin-uglify';

export default {
    plugins: [
        (process.env.NODE_ENV === 'production' && uglify() ) 
    ]
}
```
