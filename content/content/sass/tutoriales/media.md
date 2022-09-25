---
title: "Media Queries"
date: 2022-09-22T20:59:00
tags: [""]
categories: [""]
draft: false
---

En sass puedes colocar las media queries dentro del selector del elemento que vas a modificar.

```sass
.nav {
    color: blue;
    @media (min-width: 900px) {
        color: purple;
    }
    &__ola {
        width: 100px;
        height: 100px;
        background-color: aquamarine;
    }
}
```
