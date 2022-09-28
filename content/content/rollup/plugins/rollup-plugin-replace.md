---
title: "rollup-plugin-replace"
description: "" 
date: 2022-09-28T19:36:26
tags: [""]
categories: [""]
draft: false
---
Va a traspasar las varaible de ambiente creadas durante o en los procesos de rollup, al codigo final.

**install**

```jsx
npm i -D rollup-plugin-replace
```

configurar desde rollup

```jsx
import replace from 'rollup-plugin-replace';

export default {
    plugins: [
        replace({
            ENV: JSON.stringify(process.env.NODE_ENV || 'develoment');
        })
    ]
}
```
