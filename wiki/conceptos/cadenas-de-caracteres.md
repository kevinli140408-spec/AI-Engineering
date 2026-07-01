---
titulo: "Cadenas de Caracteres (Strings)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [cadenas, strings, python]
fuentes: [cadenas-caracteres-mm, joyanes-aguilar-fundamentos-de-programacion]
---

# Cadenas de Caracteres (Strings)

Una cadena (`string`, tipo `str`) es una **secuencia de caracteres**. En Python es **case sensitive** (distingue mayúsculas de minúsculas) y se delimita con comillas simples o dobles.

```python
cad1 = "Lunes"
cad2 = 'Martes'
```

## Operadores

| Operador | Función |
|----------|---------|
| `+` | Concatenar (unir cadenas) |
| `*` | Replicar (`"*" * 10` → `**********`) |
| `in` | Buscar subcadena (`"te" in cad`) |
| `==` | Comparar igualdad |

Para concatenar un número a una cadena, primero debe convertirse: `"La edad es " + str(edad)`.

## Iteración
Una cadena es **iterable**: se puede recorrer carácter por carácter con `for letra in cad:`.

## Métodos comunes

| Método | Función |
|--------|---------|
| `.isalpha()` | ¿Solo letras? |
| `.isdigit()` | ¿Solo dígitos? |
| `.isalnum()` | ¿Letras o dígitos? |
| `.isupper()` / `.islower()` | ¿Mayúsculas / minúsculas? |
| `.upper()` / `.lower()` | Convierte a mayúsculas / minúsculas |
| `.capitalize()` | Mayúscula solo la primera letra de la primera palabra |
| `.title()` | Mayúscula la primera letra de cada palabra |
| `.center(ancho, relleno)` | Centra rellenando con un carácter |
| `.ljust(ancho, relleno)` / `.rjust(ancho, relleno)` | Justifica a izquierda/derecha |
| `.zfill(ancho)` | Rellena con ceros a la izquierda (`"3".zfill(5)` → `"00003"`) |

## f-string (formato de cadenas)
```python
print(f"Legajo:{legajo} Nombre:{nombre} Nota:{nota}")
```

## Sintaxis reducida relacionada

### Operadores de asignación compuesta
| Operador | Equivale a |
|----------|-----------|
| `+=` `-=` `*=` `/=` `//=` `%=` `**=` | `x = x + y`, `x = x - y`, etc. |

## Variantes en pseudocódigo algorítmico (Joyanes Aguilar)

### Comparación basada en código de carácter
Dos cadenas se comparan carácter a carácter según el **código numérico** del juego de caracteres del lenguaje (ASCII de 7/8 bits, o Unicode de 16 bits — ver [[conceptos/representacion-de-la-informacion]]). La comparación se detiene en el primer par de caracteres distintos: `'GARCIA' < 'GOMEZ'` porque, comparando posición a posición, `A` (código 65) `<` `O` (código 79). Una cadena más larga que comparte el mismo prefijo es siempre mayor (`'LUIS ' > 'LUIS'`). Python compara cadenas exactamente de la misma forma (orden lexicográfico por código Unicode de cada carácter).

### Operaciones formales y su equivalente en Python
| Pseudocódigo (Joyanes) | Equivalente en Python |
|---|---|
| `longitud(cadena)` | `len(cadena)` |
| `cadena1 & cadena2` (concatenación) | `cadena1 + cadena2` |
| `subcadena(cadena, inicio, longitud)` | slicing: `cadena[inicio-1 : inicio-1+longitud]` |
| `indice(cadena, subcadena)` / `posicion(...)` | `cadena.find(subcadena)` (Python devuelve -1 si no la encuentra; el pseudocódigo devuelve 0) |
| `insertar(t, p, s)` | `t[:p-1] + s + t[p-1:]` (Python no tiene función `insert` nativa para strings — son inmutables) |
| `borrar(t, p, l)` | `t[:p-1] + t[p-1+l:]` |
| `cambiar(t, s1, s2)` | `t.replace(s1, s2)` |
| `valor(cadena)` / `cad(valor)` | `int(cadena)` / `str(valor)` |
| `código(car)` / `car(codigo)` | `ord(car)` / `chr(codigo)` |

A diferencia de Python (donde los strings son **inmutables** y estas operaciones se resuelven con slicing/métodos incorporados de una sola línea), el pseudocódigo algorítmico las trata como funciones explícitas que el programador puede tener que implementar manualmente combinando `subcadena`, `indice` y concatenación — ver el algoritmo de `insertar`/`borrar`/`cambiar` como ejemplo de composición de funciones más simples.

### Representación interna
En C/C++, una cadena es internamente un **array de caracteres** terminado en el carácter nulo `'\0'` — ver [[conceptos/arrays-vectores-matrices]]. Otras representaciones clásicas: longitud fija (relleno con blancos), longitud variable con máximo (puntero + longitud actual), o longitud indefinida (lista enlazada de caracteres). Python abstrae completamente esta representación: el tipo `str` se gestiona internamente sin que el programador deba pensar en arrays ni en terminadores.

## Referencias

- [[fuentes/cadenas-caracteres-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[entidades/python]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/arrays-vectores-matrices]]
