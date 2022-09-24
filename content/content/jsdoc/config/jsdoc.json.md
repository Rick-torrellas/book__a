---
title: "jsdoc.json"
date: 2022-09-08T16:24:51
tags: [""]
categories: [""]
draft: false
---

# jsdoc.json

## Next.js

```JSON
{
  "source": {
    "include": [
      "pages",
      "components",
      "lib"
    ],
    "includePattern": ".js$",
    "excludePattern": "(node_modules|docs)"
  },
  "plugins": [
    "plugins/markdown",
    "jsdoc-http-plugin",
    "node_modules/better-docs/component",
    "node_modules/better-docs/category"
  ],
  "templates": {
    "cleverLinks": true,
    "monospaceLinks": true,
    "better-docs": {
      "name": "My React components"
    }
  },
  "tags": {
    "allowUnknownTags": ["component","category"]
},
  "opts": {
    "recurse": true,
    "destination": "./docs",
    "template": "node_modules/better-docs",
    "tutorials": "./tutorials",
    "readme": "./README.md"
  }
}
```

## Basic

```JSON
{
  "source": {
    "include": ["src"],
    "includePattern": ".js$",
    "excludePattern": "(node_modules|docs)"
  },
  "plugins": [
    "plugins/markdown"
  ],
  "templates": {
    "cleverLinks": true,
    "monospaceLinks": true
  },
  "opts": {
    "recurse": true,
    "destination": "./docs",
    "tutorials": "./tutorials",
    "readme": "./README.md"
  }
}
```
