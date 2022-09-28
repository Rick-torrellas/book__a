---
title: "Cambiar el font family - Google fonts"
description: "" 
date: 2022-09-28T19:42:15
tags: [""]
categories: [""]
draft: false
---
## Establecerlo

- Seleccionamos que fonts queremos se la familia/s

![sample](C:\Users\batman\Documents\taller\book\book__txt\content\tailwind\tutorial\Screenshot%202022-04-05%20115003.png)

- Luego lo embebemos

![](C:\Users\batman\Documents\taller\book\book__txt\content\tailwind\tutorial\ded.png)

- Copiamos los links al head en el html

![](C:\Users\batman\Documents\taller\book\book__txt\content\tailwind\tutorial\html.png)

- Ahora para agregarlos se pueden hacer de dos maneras,
  
  - En el archivo donde tengas declarado tailwind.css
  
  ```jsx
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  
  @layer base {
      body {
          font-family: 'Roboto Condensed', sans-serif;
      }
  }
  ```
  
  Esto sera mas global.
  
  - En tailwind.config.js
  
  ```jsx
  module.exports = {
    content: ['./src/**/*.{html,js,svelte,ts}'],
    theme: {
      extend: {
        fontFamily: {
          roboto: "'Roboto Condensed', sans-serif"
        }
      },
    },
    plugins: [],
  }
  ```

## Uso

Para usar el font family custom que se acaba de crear (La forma 2s).

```jsx
<span class="font-bold text-2xl font-roboto" >Youtube</span>
```
