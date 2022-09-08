---
title: "Condicionales"
---

# Condicionales

> source: [If Statements | Hugo - Static Site Generator | Tutorial 19 - YouTube](https://www.youtube.com/watch?v=juSnHsCX9RU&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=24)

* **eq**: == igual que

* **lt**: < menor que

* **le**: =< menor o igual que

* **gt**: > mayor que

* **ge**: => igual o igual que 

* **not**: negacion

* **and**: &&

* **or**: ||

## If

Syntax:

```hugo
{{if operador condicion1 condicion2}}
{{end}}
```

Ejemplo:

```hugo
{{$uno := 2}}
{{$dos := 2}}
{{if eq $uno $dos}}
<p>true</p>
{{end}}
```

### else y else if

En hugo tambien es posible usar tantos `else` como `else if`, tantas veces sea necesario

```hugo
{{$uno := 2}}
{{$dos := 2}}
{{if eq $uno $dos}}
<p>true</p>
{{else if eq $dos $uno}}
<p>mas true :D</p>
{{else}}
<p>false</p>
{{end}}
```

### not

> Nota: es importante no tener espacios dentro de los limites de los parentesis, como el ejemplo o si no no funcionara.

```hugo
{{$uno := 2}}
{{$dos := 2}}
{{if not (eq $uno $dos) }}
<p>false</p>
{{end}}
```

> Nota: puedes colocar not dentro de otro not.

### and,or

```hugo
{{$uno := 1}}
{{$dos := 2}}
{{$tres := 1}}
{{if or (eq $uno $dos ) (eq $uno $tres) }}
<p>true</p>
{{end}}
```

> Nota: puedes usar un nor, dentro de una de los parentesis, solo hay que agregar mas parentesis.

### Tag property

Hugo te deja no solo insertar codigo dentro las propiedades de las etiquetas de html, si no escribir condicionales.

```hugo
<li style="{{if eq .Title $title}} background-color: red; {{end}}">{{.Title}}</li>
```
