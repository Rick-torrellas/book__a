---
title: "Servicios"
description: ""
---

Servicios
=========

Comandos para servicios
-----------------------

SC comando

Aparentenmente en windows tambien existen los servicios como tal, para programarlos hay qu aprender C#, pero se pueden crear si ya tiene el .exe. brutal :D

Tambien el comando net sirve para eso

https://ss64.com/nt/net-service.html

Desabilitar un servicio
-----------------------

Para desabilitar un servicio en windows, primero hay que desabilitar su inicio con sc

sc config servicename start= disabled

luego se tiene que parar el servicio, solo asi se puede detener un servicio. ojo solo se puede detener no se puede pausar.

Para volver a iniciar el servicio se necesita iniciar el servicio otra ver con sc

`sc config servicename start=auto`
