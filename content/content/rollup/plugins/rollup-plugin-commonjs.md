---
title: "rollup-plugin-commonjs"
description: "" 
date: 2022-09-28T19:34:54
tags: [""]
categories: [""]
draft: false
---
transforma cjs (commond js) a es5.

**install**

```jsx
npm i -D rollup-plugin-commonjs
```

configurarlo en rollup

```jsx
import commonjs from 'rollup-plugin-commonjs';

export default {
    plugins: [
        commonjs()
    ]
}
```
