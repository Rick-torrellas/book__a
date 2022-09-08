---
title: "Variables"
description: ""
---

Variables
=========

special characters en variables
-------------------------------

INVERTIGAR MAS A FONDO, a la hora de guardar una variable con algunos de los simbolos especiales, va a hacer que el archivo no se pueda abrir.

No se puede guardar variable con simbolos especiales como ">" y no sirve la guebonah esa de ^>, por que en esa ocacion al menos no se queda pegao, pero muestra el > cuando muestra el valor de la variable

```cmd
@echo off
set mysql_paran_1=Hola > Nalga
echo %mysql_paran_1%
pause
```

Resultado

Hola

Pasar argumentos de un comando con variables
--------------------------------------------

Se le puede pasar los parametros a un comando por medio de variables.

Ejemplo

```cmd
set ubicacion=c:/users/worf_/desktop/nalga
set taller_servidor=c:/users/worf_/desktop/compota
set parametro=/mir %ubicacion% %taller_servidor%
robocopy %parametro%
```
