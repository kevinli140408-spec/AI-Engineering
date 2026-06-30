---
titulo: "Variable (Programación)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [variables, tipos-de-datos, python]
fuentes: [algoritmos-secuenciales-mm, guia-estudio-algoritmia-mm]
---

# Variable (Programación)

Espacio en memoria que almacena un dato, representado mediante un nombre (identificador). Se la suele imaginar como una **caja o contenedor**: guarda un solo valor a la vez, y puede cambiar de valor durante la ejecución del programa.

## Características
- Posee un **nombre** (identificador).
- Posee un **tipo de dato**.
- Tiene asociada una **dirección de memoria RAM** (volátil: desaparece al finalizar el programa).

## Reglas de nombres
- Combinaciones de letras, números y guion bajo `_`.
- No puede comenzar con número.
- No se pueden usar palabras reservadas del lenguaje ni otros símbolos.
- Evitar `l`, `O`, `I` como nombres de una sola letra (se confunden con 1 y 0).

## Tipos de datos en Python

| Tipo | Descripción | Ejemplo |
|------|-------------|---------|
| `int` | Números enteros | `25` |
| `float` | Números reales | `7.5` |
| `str` | Texto / cadenas de caracteres | `"Lautaro"` |
| `bool` | Verdadero o falso | `True`, `False` |
| `None` | Valor "vacío" | — |

Python usa **tipado dinámico**: el tipo se deduce automáticamente al asignar el valor (no se declara explícitamente).

## Constantes
Valores fijos que no se alteran durante la ejecución. Por convención (no obligatoria) se nombran en mayúsculas.

## Operador de asignación
`=` guarda o copia un valor (constante, variable o expresión) en una variable: `a = valor`.

## Entrada y salida de datos

```python
nombre = input("Ingrese su nombre: ")     # entrada (siempre devuelve texto)
edad = int(input("Ingrese su edad: "))    # conversión a entero
print("Hola", nombre)                      # salida combinando texto y variable
```

Conversión de tipos: `int()`, `float()`, `str()`.

## Comentarios
Líneas no procesadas por el intérprete, usadas como documentación. En Python: `# comentario`.

## Referencias

- [[fuentes/algoritmos-secuenciales-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[entidades/python]]
