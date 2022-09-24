---
title: "install"
date: 2022-09-08T17:44:29
tags: [""]
categories: [""]
draft: false
---

# Install

## En Windows (PowerShell):

```powershell
iwr https://get.pnpm.io/install.ps1 -useb | iex
```

## Usando Corepack

```powershell
corepack enable
```

Esto instalará automáticamente pnpm en su sistema. Sin embargo, probablemente no sea la última versión de pnpm. To upgrade it, check what is the latest pnpm version and run:

```powershell
corepack prepare pnpm@<version> --activate
```

Usando pnpm

```powershell
Usando pnpm
```
