# Dashboard — Wiki Health

> Ejecutar estas consultas antes de llamar a `wiki-maintenance` o `weekly-review`.
> Dataview corre localmente y no consume tokens de Claude — usarlo para detectar problemas primero, luego pasarle a Claude solo los casos específicos que necesitan juicio semántico.

---

## 1. Páginas sin enlaces salientes (candidatas a huérfanas)

```dataview
list
from "wiki"
where length(file.outlinks) = 0
and tipo != "weekly-review"
```

> Si aparecen páginas aquí → decirle a Claude: "agrega wikilinks a estas páginas: [lista]"

---

## 2. Páginas con campos obligatorios faltantes

```dataview
table
  choice(!titulo, "❌", "✅") as titulo,
  choice(!tipo, "❌", "✅") as tipo,
  choice(!creado, "❌", "✅") as creado,
  choice(!actualizado, "❌", "✅") as actualizado,
  choice(!tags, "❌", "✅") as tags
from "wiki"
where !titulo or !tipo or !creado or !actualizado or !tags
```

> Si aparecen páginas aquí → decirle a Claude: "corrige el frontmatter de estas páginas: [lista]"

---

## 3. Páginas que superan ~500 palabras (candidatas a dividir)

```dataview
table file.size as "tamaño (bytes)", round(file.size / 4) as "~palabras"
from "wiki"
where file.size > 2000
sort file.size desc
```

> Si aparecen páginas aquí → decirle a Claude: "divide esta página en sub-páginas: [nombre]"

---

## 4. Páginas nuevas (últimos 7 días) sin enlaces entrantes

```dataview
list
from "wiki"
where creado >= date(today) - dur(7 days)
and length(file.inlinks) = 0
```

> Si aparecen páginas aquí → son nuevas y todavía no están enlazadas desde ninguna otra página. Decirle a Claude: "agrega backlinks a estas páginas desde las páginas relacionadas: [lista]"

---

## 5. Resumen por tipo (visión general)

```dataview
table rows.file.link as páginas, length(rows) as total
from "wiki"
where tipo
group by tipo
```

---

## 6. Todos los tags existentes y cuántas páginas los usan

```dataview
table length(rows) as total, rows.file.link as páginas
from "wiki"
where tags
flatten tags as tag
group by tag
sort length(rows) desc
```

> Tags que aparecen solo 1 vez → probablemente son variantes de otro tag ya existente (ej: `matematica` vs `matemáticas`). Decirle a Claude: "unifica estos tags: [lista]"
> Tags con nombres muy similares → candidatos a consolidar en uno solo.

## 7. Conceptos raices
```dataview
table length(rows) as total, rows.file.link as páginas
from "wiki"
where tags
flatten tags as tag
group by tag
sort length(rows) desc
limit 20
```

**Flujo de mantenimiento recomendado**

| Frecuencia | Acción |
|---|---|
| Después de cada ingest | Abrir este dashboard, revisar consultas 1 y 4 |
| Cada semana | Correr `weekly-review` (lee solo los cambios de la semana) |
| Cada mes | Correr `wiki-maintenance` completo (scan global) + revisar consulta 6 para limpiar tags |
