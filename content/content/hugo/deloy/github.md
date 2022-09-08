---
title: "Github"
date: 2022-09-08T12:19:08
tags: [""]
categories: [""]
draft: false
---
# Github

> source: [youtube](https://www.youtube.com/watch?v=psyz4UPnGAA)

> source: [official docs](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

## Primera manera

Esta es la mas secilla. Simplemente vamos a construir nuestro sitio en una carpeta llamada `docs`, y configurar Github Pages para que agarre esta carpeta como la central del sitio. Usaremos este comando.

`hugo -d docs --minify`

## Segunda manera

### Build Hugo With GitHub Action

Crear un archivo en `.github/workflows/gh-pages.yml`, en tu proyecto.

```YAML
name: github pages

on:
  push:
    branches:
      - main  # Set a branch to deploy
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-20.04
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: true  # Fetch Hugo themes (true OR recursive)
          fetch-depth: 0    # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          # extended: true

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: github.ref == 'refs/heads/main'
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

### Configurar la ramas

En github vamos a configurar para que use la rama `gh-pages`, ` Configuracion > Pages > Branch > pg-pages `.

### Change baseURL in config.toml

Don’t forget to rename your baseURL in config.toml with the value.  

`https://<USERNAME>.github.io` for your user repository or
`https://<USERNAME>.github.io/<REPOSITORY_NAME>` for a project repository.

### Use a Custom Domain

If you’d like to use a custom domain for your GitHub Pages site, create a file static/CNAME. Your custom domain name should be the only contents inside CNAME. Since it’s inside static, the published site will contain the CNAME file at the root of the published site, which is a requirement of GitHub Pages.

Refer to the [official documentation for custom domains](https://help.github.com/articles/using-a-custom-domain-with-github-pages/) for further information.
