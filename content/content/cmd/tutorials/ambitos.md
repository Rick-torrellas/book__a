---
title: "Ambitos"
description: "" 
date: 2022-09-28T18:34:44
tags: [""]
categories: [""]
draft: false
---
## Iniciar un ambito

Al iniciar un archivo este siempre lo hace desde el ambito global del archivo, pero cuando llamas a una subroutine, este ambito cambia a esa subroutine hasta que termine, si se quiere usar %0, para expresar donde se esta en el archivo, hay que hay una llamada inicial.

Tambien tienes que tener en cuanta que este comportamiento es valido solo para call, incluso goto ni permite pasar parametro a la hora de brican al codigo, call y goto son diferentes.

El unico que puede cambiar la subtoutine es call, incluso si el flujo del script te cambia la subroutine esta permanece en donde fue llamada.

## Salir del ambito

exit /b , se utiliza para salir de una subroutine o un bloque de codigo, estos bloques pueden ser for o codigo encerrado en una etiqueta :etiqueta, esto te permite crear una manera de salir de ese entorno para que el script continue ejecutandose, justo despues de donde se llamo, mira el siguiente ejemplo

```cmd
@echo off
echo hola
call :hola
echo estas
pause
:hola
echo como
exit /b
echo Mierda
pause
```
La etiqueta :hola Lo que se va a imprimir por pantalla sera hola como estas, y se va a oviar el "Mierda", ya que se esta saliendo es del:hola y no del script, este comportamiento es similar a tener una funcion dentro del script, brutal