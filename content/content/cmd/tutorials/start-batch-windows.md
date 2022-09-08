---
title: "Ejecutar un script al iniciar windows"
description: ""
---

Ejecutar un script al iniciar windows
=====================================

En windows, existe una carpeta donde estan los accesos directos a programas que se inician con el, si se copia un archivo como un batch un exe, en teoria deberia iniciar con windows, esta es la direccion de dicha carpeta.

Para iniciar scripts, al iniciar windows, se tienen que colocar en la siguiente ruta.

`C:\Users\worf_\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup`

Tambien puedes acceder ella usando: windows+r - shell:startup

La segunda manera de hacer esto es por medio del registro, lo cual requiere saber del comando reg, aqui va el ejemplo

```cmd
            reg add "HKLM\Software\Microsoft\Windows\CurrentVersion\Run" /v
            "UNNOMBREQUESEMOSTRARA" /d "c:\tubat.bat"
            ::reg add es para agregar la clave
            ::HKLM\Software\Microsoft\Windows\CurrentVersion\Run es la entrada
            magica donde estan todos los programas q se inician cn windows...
            ::/v indica el nombre del valor
            ::/d indica los datos que seran agregados
```
