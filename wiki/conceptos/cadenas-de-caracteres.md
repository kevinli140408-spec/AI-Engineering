---
titulo: "Cadenas de Caracteres (Strings)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [cadenas, strings, python]
fuentes: [cadenas-caracteres-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, programacion1-cadenas1-thompson, programacion1-cadenas2-thompson]
---

# Cadenas de Caracteres (Strings)

Una cadena (`string`, tipo `str`) es una **secuencia de caracteres**. En Python es **case sensitive** (distingue mayúsculas de minúsculas) y se delimita con comillas simples o dobles.

```python
cad1 = "Lunes"
cad2 = 'Martes'
```

Python 3 usa codificación **UTF-8**, que admite caracteres regionales (`ñ`, vocales acentuadas) sin configuración adicional — a diferencia de Python 2, que usaba ASCII por defecto. Usar comillas distintas a las de apertura permite incluir el otro tipo sin escapar (`"Mc. Donald's"`); una cadena larga puede partirse en varias líneas de código con `\` al final de cada línea (sin que eso inserte un salto de línea en el resultado), a diferencia de las cadenas multilínea con `'''`/`"""` (que sí conservan los saltos de línea reales).

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
| `.lstrip([cad])` / `.rstrip([cad])` / `.strip([cad])` | Elimina los caracteres de `cad` (por defecto, espacios) al comienzo / al final / en ambos extremos |
| `.find(cad, ini, fin)` / `.rfind(...)` | Como `.index()`, pero devuelve `-1` en vez de lanzar error si no encuentra la subcadena (`rfind` busca desde el final) |

## f-string (formato de cadenas)
Introducidas en Python 3.6 (2016), simplifican el formateo frente al operador `%` o `.format()`: una cadena precedida por `f` inserta el valor de cualquier variable, expresión o llamada a función/método escrita entre llaves (**marcador de posición**):

```python
dia, mes = 16, "Enero"
print(f"Sucedió el {dia} de {mes}.")   # Sucedió el 16 de Enero.
print(f"{2 * 37}")                      # 74 (expresión)
print(f"{mes.lower()}")                 # enero (método)
```

El formato de cada marcador admite las mismas opciones que `.format()` (ancho, alineación, relleno, decimales), escritas tras `:`:

```python
num, pal = 15, "Hola"
f"*{num:5}*"      # *   15*   ancho 5, alinea números a la derecha por defecto
f"*{num:05}*"     # *00015*   0 delante del ancho rellena con ceros
f"*{num:<8}*"     # *15      *  forzar alineación a la izquierda
f"*{pal:>8}*"     # *    Hola*  forzar alineación a la derecha (cadenas se alinean a la izquierda por defecto)
f"*{pal:^8}*"     # *  Hola  *  centrado
f"*{pal:=^8}*"    # *==Hola==*  carácter de relleno personalizado antes del símbolo de alineación
f"{3.1416:8.2f}"  # "    3.14"  ancho 8, 2 decimales, tipo f (punto fijo)
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

## Copia de cadenas: siempre es una referencia
A diferencia de las listas (donde hay que elegir una técnica específica para lograr una copia independiente), copiar una cadena **siempre** copia solo la referencia, sin importar la técnica: `b = a`, `c = a[:]`, `d = str(a)` y `e = a + ""` producen todas el mismo `id()` que `a`. Esto es consistente y no representa un riesgo (a diferencia del aliasing en listas) porque las cadenas son **inmutables**: no existe una operación que module el contenido de la cadena original a través de una de esas referencias, así que Python evita crear copias idénticas innecesarias en memoria. También carecen de método `reverse()` (no aplicable a un tipo inmutable); para invertir una cadena se usa la misma técnica de rebanada que en listas: `original[::-1]`.

## Cadena vs. identificador
Error común al empezar a programar: confundir una cadena con el nombre de una variable. `a = 1` crea una variable; `'a'` es una cadena de un carácter que no tiene relación alguna con la variable `a`. Olvidar las comillas de una cadena provoca que Python la interprete como un identificador (y falle con `NameError` si no existe); poner comillas de más alrededor de un nombre de variable hace que Python la trate como texto literal en vez de evaluarla ([[fuentes/introduccion-a-la-programacion-con-python-3]]).

## Conversión cadena ↔ lista
`cadena.split(sep=' ')` parte una cadena en una lista de subcadenas usando `sep` como separador (por defecto, espacio en blanco, e ignora espacios repetidos/al borde); `separador.join(lista)` hace lo inverso: une los elementos de una lista de cadenas en una sola, intercalando `separador` entre cada uno. `list(cadena)` convierte una cadena en una lista de sus caracteres individuales. Son las herramientas más usadas para pasar de texto libre a datos estructurados y viceversa ([[fuentes/introduccion-a-la-programacion-con-python-3]]).

## Secuencias de escape
La barra invertida `\` es el **carácter de escape**: indica que el carácter siguiente tiene un significado especial en vez de literal ([[fuentes/introduccion-a-la-programacion-con-python-3]]). Las más usadas: `\n` (salto de línea), `\t` (tabulador horizontal, útil para alinear en columnas), `\\` (barra invertida literal), `\'`/`\"` (comilla literal dentro de una cadena delimitada por el mismo tipo de comilla). También existen cadenas **raw** (`r'...'`), que desactivan por completo la interpretación de escapes (útiles para rutas de archivo o expresiones regulares), y **cadenas multilínea** delimitadas con `'''...'''` o `"""..."""`. Nota histórica: Unix marca fin de línea solo con `\n`, Windows con `\r\n`, y los Macintosh clásicos usaban solo `\r` — de ahí los problemas de compatibilidad al mover archivos de texto entre sistemas operativos.

## El método `format`
`'{0} tiene {1} años'.format(nombre, edad)` interpola valores en una cadena: cada marca `{n}` se sustituye por el argumento `n`-ésimo de `format` (contando desde 0). Puede controlarse con precisión el aspecto del valor mostrado mediante una **marca de formato**: `[[relleno]alineamiento][signo][#][0][ancho][.precisión][código de tipo]`, por ejemplo `'{0:>10.2f}'.format(x)` alinea a la derecha en 10 espacios con 2 decimales. Alineamiento: `<` izquierda, `>` derecha (por defecto), `^` centrado. Códigos de tipo comunes: `b`/`o`/`x` (binario/octal/hex para enteros), `f` (punto fijo), `e` (notación exponencial), `%` (porcentaje). Las llaves literales se escapan duplicándolas: `{{` y `}}`.

## Referencias

- [[fuentes/cadenas-caracteres-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-cadenas1-thompson]]
- [[fuentes/programacion1-cadenas2-thompson]]
- [[entidades/python]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/expresiones-regulares]]
