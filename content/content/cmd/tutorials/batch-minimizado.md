---
title: "Ejecutar un batch minimizado"
description: ""
---

# Ejecutar un batch minimizado

Desde otro batch.  

Para iniciar otro batch minimizdo.  

```cmd
cmd.exe /c & start "" /min aplication.cmd
```

Desde el mismo batch.  

Para iniciar el batch minimizado.  

```cmd
if not DEFINED IS_MINIMIZED set IS_MINIMIZED=1 && start "" /min "%~dpnx0" %* && exit
```
