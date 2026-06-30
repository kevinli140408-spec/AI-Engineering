---
titulo: "Cadenas de Caracteres (Strings)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [cadenas, strings, python]
fuentes: [cadenas-caracteres-mm]
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

## Referencias

- [[fuentes/cadenas-caracteres-mm]]
- [[entidades/python]]
