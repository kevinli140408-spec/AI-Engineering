---
titulo: "Expresiones Regulares"
tipo: concepto
creado: 2026-09-09
actualizado: 2026-09-09
tags: [expresiones-regulares, regex, python, modulo-re]
fuentes: [programacion1-expresiones-regulares-thompson]
---

# Expresiones Regulares

Una **expresión regular** (regex) es una secuencia de caracteres que forma un **patrón de búsqueda**, usado para encontrar coincidencias (y contar repeticiones) dentro de texto, o para validar que un texto cumpla un formato determinado (direcciones de correo, códigos de inventario, patentes vehiculares, etc.). En Python, todas las funciones para trabajar con expresiones regulares están en el módulo `re`.

## Funciones principales

| Función | Función |
|---|---|
| `re.search(patrón, cadena)` | Busca la **primera** coincidencia; devuelve un objeto `re.Match`, o `None` si no encuentra nada |
| `re.findall(patrón, cadena)` | Busca **todas** las coincidencias; devuelve una lista de cadenas (vacía si no hay coincidencias) |
| `re.sub(patrón, reemplazo, cadena)` | Reemplaza **todas** las coincidencias de `patrón` por `reemplazo`; devuelve una cadena nueva (o la misma, sin cambios, si no encuentra nada) |

```python
import re
cad = "La bella y graciosa moza se marchó a lavar la ropa"
resultado = re.search("moza", cad)      # <re.Match object; span=(20, 24), match='moza'>
resultado.start(), resultado.end()      # 20, 24 — dónde empieza/termina la coincidencia

re.findall("la", cad)                   # ['la', 'la', 'la']
re.sub("bella.* la", "[...]", cad)      # "La [...] ropa"
```

Puede agregarse el parámetro `re.IGNORECASE` a `search`/`findall` para que la búsqueda ignore mayúsculas/minúsculas.

## Metacaracteres (comodines)
Símbolos con significado especial dentro del patrón:

| Metacarácter | Significado |
|---|---|
| `.` | Cualquier carácter |
| `^` | Ancla de **inicio**: el patrón debe aparecer al comienzo de la cadena |
| `$` | Ancla de **fin**: el patrón debe aparecer al final de la cadena |
| `[abc]` | Cualquiera de los caracteres del grupo |
| `[a-d]`, `[0-9]`, `[P-Z]` | Rango de caracteres (equivalente a listarlos todos) |

Los anclas se combinan libremente con grupos y rangos: `^[b-k]` coincide solo si el primer carácter de la cadena está entre `b` y `k`.

## Cuantificadores
Indican cuántas veces debe repetirse el carácter (o grupo) que los antecede:

| Cuantificador | Significado |
|---|---|
| `?` | 0 o 1 vez |
| `*` | 0 o más veces |
| `+` | 1 o más veces |

Ejemplo: con la lista `["12", "102", "1002", "10002"]`, el patrón `10?2` (el `0` es opcional) coincide con `"12"` y `"102"`; el patrón `10+2` (uno o más `0`) coincide con `"102"`, `"1002"` y `"10002"`.

## Relación con otras herramientas de texto
Las expresiones regulares son un mecanismo más potente y general que los métodos de cadena vistos en [[conceptos/cadenas-de-caracteres]] (`.find()`, `.replace()`, `.split()`): estos últimos buscan texto literal o un separador fijo, mientras que una regex describe una **familia** de posibles coincidencias (cualquier dígito, cualquier repetición, solo al inicio/fin, etc.) en una sola expresión compacta.

## Referencias

- [[fuentes/programacion1-expresiones-regulares-thompson]]
- [[entidades/python]]
- [[conceptos/cadenas-de-caracteres]]
