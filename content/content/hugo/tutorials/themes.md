---

title: "Themes"

---

# Theme

Cada tema se puede instalar de diferente manera.

## Submodulos

Creo que todos pueden ser instalados como submodulos.

```git
git submodule add https://github.com/EmielH/tale-hugo.git themes/tale
```

## Establecer tema

En el archivo `config.toml`, coloca lo siguiente:

```toml
theme = "tale"
```

o tambien puede usar el comando

```
hugo server -t tale
```
