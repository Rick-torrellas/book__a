---
title: "Loaders"
description: "" 
date: 2022-09-28T19:39:12
tags: [""]
categories: [""]
draft: false
---
Los loaders te permiten acceder a cierta informacion y fetch data.

Hasta ahora se puede acceder a esta informacion.

- url
- params
- props
- fetch
- session
- stuff
- status
- error

url tiene informacion, justamente de la url 😀

Hasta la fecha estos son los valores que el objeto url contiene.

## Ejemplo de url

```jsx
URL {
  href: '<http://localhost:3000/>',
  origin: '<http://localhost:3000>',
  protocol: 'http:',
  username: '',
  password: '',
  host: 'localhost:3000',
  hostname: 'localhost',
  port: '3000',
  pathname: '/',
  search: '',
  searchParams: URLSearchParams {},
  hash: ''
}
```

```jsx
<script context="module">
    export async function load({url}) {
    return {
      props: {
        url
      },
      // context: {'message': 'sup'}
    }
  }
</script>
<script>
    export let url;
    console.log(url);
</script>
<h1>Book</h1>
<a href="/test">test</a>
<p>{url.pathname}</p>
```

## 
