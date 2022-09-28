---
title: "Self-hosting fonts with @font-face rules"
description: "" 
date: 2022-09-28T19:42:47
tags: [""]
categories: [""]
draft: false
---
Esto quiere decir fuentes locales

- En el archivo de css, agregaremos:

```jsx
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
    @font-face {
        font-family: "roboto";
        font-weight: 400;
        font-style: normal;
        src: url(/fonts/roboto-400.woff2) format("woff2"), url(/fonts/roboto-400.woff) format("woff")
    }
}
```

Para espesificar varios, se puede duplicar el @font-face.

## Uso

```jsx
<span class="font-bold text-2xl font-roboto" >Youtube</span>
```
