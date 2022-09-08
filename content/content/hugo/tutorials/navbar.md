---

title: "Barra de navegacion"

---

# Barra de navegacion

Existen varias manera de establecer un menu

* config.toml

```
[menu]
  [[menu.main]]
    identifier = "about"
    name = "About"
    title = "About"
    url = "/about/"
    weight = 0
  [[menu.main]]
    identifier = "posts"
    name = "Posts"
    title = "Posts"
    url = "/posts/"
    weight = 0
```
