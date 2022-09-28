---
title: "Install"
description: "" 
date: 2022-09-28T19:40:19
tags: [""]
categories: [""]
draft: false
---
## Install next.js

```jsx
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

**Configure your template paths**

Add the paths to all of your template files in your **`tailwind.config.js`** file.

```jsx
tailwind.config.js

module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

**Add the Tailwind directives to your CSS**

Add the **`@tailwind`** directives for each of Tailwind’s layers to your **`./styles/globals.css`** file.

```jsx
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Install sveltekit

```jsx
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init tailwind.config.cjs -p
```

Si estas usando prettier, cambiar el archivo .prettiertc (esto es opcional)

```jsx
{
    "useTabs": true,
    "singleQuote": true
}
```

archivo tailwind.config.cjs

```jsx
module.exports = {
  content: ['./src/**/*.{html,js,svelte,ts}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Este me da error:

```jsx
module.exports = {
  content: ['./src/**/*.{html,js,svelte,ts}'],
  theme: {
    extend: {},
  },
  plugins: [module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
}
```

Crear un archivo llamado **postcss.config.cjs**

```jsx
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

Crear un archivo ./src/app.css

```jsx
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
```

Crear un archivo **./src/routes/__layout.svelte**

```jsx
<script>
  import "../app.css";
</script>

<slot />
```
