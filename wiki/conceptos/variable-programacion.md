---
titulo: "Variable (Programación)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [variables, tipos-de-datos, python]
fuentes: [algoritmos-secuenciales-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, programacion1-introduccion-thompson, programacion1-cadenas1-thompson]
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

### Formato con el operador `%` (estilo antiguo)
Además de f-strings y `.format()` (ver [[conceptos/cadenas-de-caracteres]]), Python soporta un estilo de formateo más antiguo con **especificadores de conversión** y el operador `%`:

```python
cant, precio = 10, 12.5
print("Cantidad: %6d" % cant)     # Cantidad:     10
print("Precio: %7.2f" % precio)   # Precio:   12.50
print("%04d" % 3)                 # 0003  (relleno con ceros)
print("X = %4d Y = %4d" % (x, y)) # varias variables: van entre paréntesis
```

- `%d`: entero. `%f`: real. `%s`: cadena de caracteres (también admite ancho: `"%10s" % nombre`).
- El primer número tras `%` es el **ancho total**; el segundo (tras el punto), la **cantidad de decimales**.
- Un `0` antes del ancho rellena con ceros en vez de espacios.

## Comentarios
Líneas no procesadas por el intérprete, usadas como documentación. En Python: `# comentario`.

## Equivalente en pseudocódigo algorítmico
En notación independiente del lenguaje (Joyanes Aguilar), los tipos básicos son **entero**, **real**, **lógico** y **carácter/cadena**, declarados explícitamente (`var entero: Edad`) a diferencia del tipado dinámico de Python. Tablas de operadores, precedencia y funciones internas en [[conceptos/operadores-y-expresiones]].

## La asignación no es una ecuación
Aunque `x = x + 1` parezca una ecuación sin solución (`0 = 1`), una asignación en Python (y en la mayoría de lenguajes imperativos) es una **acción en dos pasos**, no una igualdad matemática ([[fuentes/introduccion-a-la-programacion-con-python-3]]): (1) se evalúa primero la expresión de la derecha del `=` usando el valor *actual* de las variables involucradas, y (2) el resultado se guarda en la variable de la izquierda, sobrescribiendo su valor anterior. Confundir `=` (asignación) con `==` (comparación de igualdad) es un error frecuente al empezar a programar.

## Modelo de memoria de una asignación
Al asignar un valor a una variable que no existía, Python reserva un espacio en memoria, almacena el valor y crea una asociación entre el identificador y la dirección de memoria de ese espacio — de ahí que una variable "recuerde" siempre el último valor asignado, hasta la siguiente asignación.

## Variables no inicializadas
A diferencia de otros lenguajes, en Python la primera operación sobre una variable debe ser necesariamente una asignación: usar una variable sin haberla inicializado antes produce la excepción `NameError` ("name '...' is not defined"). No existen variables "vacías" o con valor por defecto implícito.

## Reglas de identificadores (detalle Python)
Un identificador se forma con letras (de cualquier alfabeto — `π` es válido), dígitos y guion bajo `_`, sin poder empezar por un dígito, y no puede coincidir con una palabra reservada. Python distingue mayúsculas de minúsculas (`area`, `Area` y `AREA` son tres identificadores distintos). Palabras reservadas de Python 3: `and, as, assert, break, class, continue, def, del, elif, else, except, False, finally, for, from, global, if, import, in, is, lambda, nonlocal, None, not, or, pass, raise, return, True, try, with, while, yield`.

## Referencias

- [[fuentes/algoritmos-secuenciales-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-introduccion-thompson]]
- [[entidades/python]]
- [[conceptos/operadores-y-expresiones]]
