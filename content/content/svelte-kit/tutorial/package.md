---
title: "Create Package"
description: "" 
date: 2022-09-28T19:39:26
tags: [""]
categories: [""]
draft: false
---
- Lo primero que tienes que hacer, es crear una carpeta “lib”, en “/src/lib.
  
  - Recordar que se pueden usar arhivos js, para exportar un numero de componentes svelte. Tambien se puede exportar tan solo un componente svelte, para eso tendras que espesificarlo, en el siguiente paso lo explico.

- exportar el contenido, por defecto, si tienes un archivo index.js o svelte, dentro de lib, svelte automaticamente lo tomara, pero en caso de que no sea el caso, dentro del package.json, tendras que crear un objecto. Ten en cuenta que el Autoform, esta ubicado en lib, pero asi es la manera que tendras que representarlo:
  
  ```jsx
  "exports": {
      ".": "./AutoForm.svelte"
  }
  ```

Tambien hace falta instalar estas dependencias

```jsx
npm i -D svelte2tsx typescript
```

y crear un archivo **jsconfig.json**

```jsx
{
    "extends": "./.svelte-kit/tsconfig.json"
}
```

- Lo ultimo es sensillo, sinplemnte ejecuta, esto creara una carpeta con tu paquete.

```jsx
npm run package 
o
svelte-kit package
```

- y por ultimo para publicarlo:

```jsx
npm publish ./package
```

Documentacion: [](https://kit.svelte.dev/docs/packaging)[Packaging • Docs • SvelteKit](https://kit.svelte.dev/docs/packaging)
