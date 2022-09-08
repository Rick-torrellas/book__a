---

title: "Templates"

---

# Templates

> source: https://www.youtube.com/watch?v=gnJbPO-GFIw&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=11

Los templates son como modelos que se van a usar para definir cada parte de nuestra web, son usados generalmente para crear **themes**, pero tambien pueden usarse sin ellos, y estan escritos con HTML,CSS,JS y GO. muy parecido a como funciona wordpress.

Todos los templates se cran dentro de estas carpetas, ya sea que vayas a ejecutarlo dentro de tu proyecto o vayas a crear un theme: `layouts/_default `

> Si tienes un tema y usas los templates estos van a sobrescribir los estes usando en el theme.

Basicamente todos usaran el mimo sistema, parecido a PHP y wordpress, donde se pueden insertar variables directamente dentro del HTML, usando esta syntaxis

<!DOCTYPE html>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>archivo lista</h1>
    {{.Content}}
</body>
</html>
```

Tambien se puede usar bucles asi.

```html
 {{range .Pages}}
    <a href="{{.Permalink}}">{{.Title}}</a>
    {{end}}
```

## List Page

> Source: https://www.youtube.com/watch?v=8b2YTSMdMps&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=12

Sirve para lista los archivos que estan dentro de una carpeta.

Para empezar vamos a crear el archivo `layouts/_default/list.html`.

## Sigle Pages

> source: https://www.youtube.com/watch?v=ZYQ5k0RQzmo&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=13

Son las paginas que renderizan el contenido estatico, vienen a ser la mayoria del contenido mostrado en la pagina.

Para definirlo creamos un archivo: `layouts/_default/single.html`.

## Home Pages

> source: https://www.youtube.com/watch?v=ut1xtRZ1QOA&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=14

Es la pagina principal del sitio web, por defecto agarra el template del list page, pero podemos crear uno especial para la pagina principal.

Para crear nuestro template crearemos el archivo: `layout/index.html`.

## Section Pages

> source: [Section Templates | Hugo - Static Site Generator | Tutorial 15 - YouTube](https://www.youtube.com/watch?v=jrMClsB3VsY&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=15)

Son para crear templates espesiciales para una section, por ejemplo si tenemos una carpeta llamada post, dentro de nuestra web, podemos darle una apariencia unica al contenido a esa section.

Podemos crear tanto `single pages` como `list pages`, para crearlo vamos: `layout/<section-name>/single|list.html

## Base Templates & Blocks

> source: [Base Templates &amp; Blocks | Hugo - Static Site Generator | Tutorial 16 - YouTube](https://www.youtube.com/watch?v=QVOMCYitLEc&list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3&index=16)

Este es un template que va a ser usado en todos los ecenarios, puede usarse como sigle list y homepage.

Para crearlo crearemos un archivo: `layout/_default/baseof.html`

Los `block` es una manera de crear componentes, en hugo.

```go
baseof.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    {{ block "block-name" .}}
    Default Value
{{end}}
</body>
</html>
single.html
{{define "block-name"}}


{{end}}
```

Esto es perfecto para crear una platilla de todo el sitio web y no tener que precuparse por volver a crear todo, cada vez que crees el single, list o index.html.

Tambien sirve para indicar contendido por defecto en caso de que alguno no este declarado, por ejemplo

```html
{{ block "header" .}}
    Default Value
{{end}}
{{ block "main" .}}
    Default Value
{{end}}
{{ block "footer" .}}
    Default Value
{{end}}
```

Tambien nos perte declarar un elemnto aparte, en caso de qu eno se quiera usar el delcarado en baseof.html

```html
single.html
{{define "header"}}

    Single solo para single
{{end}}


{{define "main"}}
Contenido main de single

{{end}}
```

> Nota: Si no tienes los blocks definido, el single,list,index.html, van a sustituir el baseof
