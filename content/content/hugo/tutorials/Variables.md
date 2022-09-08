---

title: "Variables"

---

# Variables

Las variables solo se pueden usar dentro de los templates.

Hugo viene que con un monton de variables.

Tambien puedes crearte tus propias variables para eso, en el font matter.

```yaml
---
varName: "value"
---
```

Para acceder a esta variable:

```html
<p>{{.Params.varName}}</p>
```

> Nota: si no defines la variable, no mostrra nada, no dara error ni mostrara undefined.

Tambien puedes declarar las variables dentro de la plantilla.

```html
{{$variable := "Variable"}}
single.html
{{$variable}}
```
