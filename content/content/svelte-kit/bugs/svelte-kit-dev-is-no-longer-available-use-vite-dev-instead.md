---
title: "svelte-kit dev is no longer available — use vite dev instead"
description: "" 
date: 2022-09-28T19:38:32
tags: [""]
categories: [""]
draft: false
---

# svelte-kit dev is no longer available — use vite dev instead

1. Install vite as a devDependency with npm/pnpm/etc
2. Create a vite.config.js with the @sveltejs/kit/vite plugin (see below)

vite.config.js

```jsx
import { sveltekit } from '@sveltejs/kit/vite';

/** @type {import('vite').UserConfig} */
const config = {
        plugins: [sveltekit()]
};

export default config;
```

1. Update your package.json scripts to reference `vite dev` instead of `svelte-kit dev, cambiar los comandos, build, dev, preview.
