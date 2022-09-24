---
title: "Windows"
date: 2022-09-08T17:13:20
tags: [""]
categories: [""]
draft: false
---

# Windows

## Install

- Desistalar npm si lo tienes instalado.
- [https://github.com/coreybutler/nvm-windows/releases](https://github.com/coreybutler/nvm-windows/releases)
- Descargar **[nvm-setup.zip](https://github.com/coreybutler/nvm-windows/releases/download/1.1.9/nvm-setup.zip), de la vercion que quieras**

## Basic

execute command nvm list available from cmd or gitbash or powershell, this will list all available version of node

```node
nvm list available
```

use command nvm install version e.g. nvm install 12.14.0 to install on the machine

```javascript
nvm install version e.g. nvm install 12.14.0
o
nvm install lts
o
nvm install latest
```

last once installed use nvm use version to use newer version e.g. nvm use 12.14.0

```javascript
nvm use version e.g. nvm use 12.14.0
```

### Upgrading nvm-windows

To upgrade nvm-windows, run the new installer. It will safely overwrite the files it needs to update without touching your node.js installations. Make sure you use the same installation and symlink folder. If you originally installed to the default locations, you just need to click "next" on each window until it finishes.
