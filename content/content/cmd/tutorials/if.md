---
title: "If"
description: ""
---

# If

## Colocar un choice dentro de un if

```cmd
set /p control_archivo_new=Indica la nueva ruta fuente: \Ejm\: C:\Vaginas\Pelulas --
if /i exist %control_archivo_new% (echo nueva ruta VALIDA) else (
echo:
echo XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
echo 		ERROR
echo    --------------------
echo:
echo Ruta no valida - %control_archivo_new%
choice /c 123 /n /m "		|1| Volver a empezar -- |2| Regresar a inicio -- |3| Regresar al menu principal -- |4| Salir"
if errorlevel 4 call "%ruta_exit%"
if errorlevel 3 call "%ruta_main%"
if errorlevel 2 goto :home
if errorlevel 1 goto :set_valores_all
)  
```

## Comprar una string con una variable

PARA PODER COMPARAR UNA STRING CON UNA VARIABLE, AL MENOS CON UNA VARIABLE NO SE EL RESULTADO CON UNA STRING.  

EL COMPORTAMIENTO DEL IF SERA QUE SI NO COLOCAS LA STRING ENTRE "" COMILLLAS ENTONCES NO LEERA EL CONETENIDO DE LA MISMA STRING.  

```cmd
if "%taller%"==NONE (goto :ruta_a_off) no leera el contenido del NONE
```

PARA QUE FUNCIONE CORRECTAMENTE SE NECESITA.  

```cmd
if "%taller%"=="NONE" (goto :ruta_a_off)
```

ERROR al usar multi comentarios.  

Al colocar mas de un comentario de un if producira que salga el siguiente mensaje en vez del comentario "El sistema no puede encontrar el controlador especificado.", y probe que solo pasa dentro de un if.  

Como en el siguiente ejemplo.  

```cmd
@echo off
set nalga=culo
if /i "%nalga%"=="%nalga%" (
echo xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
:: Hola
:: Hola
:: Hola
echo:
echo            Modulo de Respaldo a la Base de Datos!
echo:
)
pause
```

## Espacios en blanco

Si colocas espacios en blanco dentro de un if, esto causara que se salga automaticamente del batch, este comportamiento no es normal en un batch, tu puedes colocar espacios tranquilamente como en el segundo ejemplo, no dara error y no mostrara los espacios en el batch.  

```cmd
if /i exist %xampp% (
:: NALGA

	echo     El programa xampp esta instalado correctamente
)else (echo No se consiguio el programa xampp)














echo HOLA








echo NALGA
```

## meter un if dentro de otro if

```cmd
	if /i exist %xnube_b% (
	echo La ruta %nube_B_name% esta ACTIVADA: %xnube_b%
    if /i "%ubicacion%"=="%nube_B%" (echo Ya existe un respaldo de %nombre% en %nube_B_name%: "%nube_B%") else (echo Todabia no existe un respaldo de %nombre% en: "%nube_B%")
	) else (echo La ruta %nube_B_name% %xnube_b% no esta disponible)
		</code></pre>
		<p>otro ejemplo</p>
		<pre><code>
			if /i "%ubicacion%"=="%taller_servidor%" (echo Actualmente te encuentras en esta ubicacion) else (
if /i exist %xtaller_servidor% (
	echo La ubicacion taller servidor se encuentra ACTIVADA: %xtaller_servidor%
	if /i exist "%taller_servidor%" (echo Ya existe un respaldo de %nombre% en taller servidor: "%taller_servidor%") else (echo Todabia no existe un respaldo de %nombre% en taller respaldo: "%taller_servidor%")
	) else (echo La ubicacion taller servidor se encuentra DESACTIVADA: %xtaller_servidor%)
)
```

## ERROR al comprar variables

TEner cuidado al comprar 2s variables, en algunos casos al encerrar las vairalbes en [], no va a reconocer la compracion, es mejor simplemente comparar las variables.  

## ERROR comentario entre elses

Si tienes 2s elses termiando una cadena de ifs, al colocar un comentario entre ellas producira un error y se saldra del batch de una.  

```cmd
)else (echo La ruta mysql se encuentra DESABILITADA)
:: Final del if de segundo nivel 
)else (echo No se consiguio el programa xampp)
:: Final del if central
```

## ERROR terminar un else

Al colocar un else tiene que estar antecedido del cierre del if que lo precede.
)else(, en estos casos dara error, dira que else no es reconocido como un comando interno.  

```cmd
			)
else (

o
 
echo: )
else (
```
