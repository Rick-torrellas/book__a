---
title: "Agregar fonts a fonts ya existentes de tailwind"
description: "" 
date: 2022-09-28T19:41:57
tags: [""]
categories: [""]
draft: false
---
En el archivo tailwind.config.js

```jsx
const defaultTheme = require('tailwindcss/defaultTheme');
module.exports = {
  content: ['./src/**/*.{html,js,svelte,ts}'],
  theme: {
    extend: {
      fontFamily: {
        mono: ['DM Mono', ...defaultTheme.fontFamily.mono]
      }
    },
  },
  plugins: [],
}
```
