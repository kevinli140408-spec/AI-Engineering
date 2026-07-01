---
titulo: "Arrays: Vectores y Matrices"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [arrays, vectores, matrices, estructuras-de-datos, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Arrays: Vectores y Matrices

Un **array** es una estructura de datos **estática**, **homogénea** (todos sus elementos son del mismo tipo) y de **acceso directo** (indexado): el tamaño se fija al declararlo y no cambia en tiempo de ejecución. Contrasta con [[conceptos/listas-python|las listas de Python]], que son dinámicas (crecen/encogen con `append`/`pop`) — un array es más parecido a una lista de tamaño fijo creada de antemano.

## Arrays unidimensionales (vectores)
Declaración: `array[límite_inferior..límite_superior] de <tipo>` — por convención suele usarse base 1 (`1..N`), a diferencia del índice 0 de Python. El **rango** es la cantidad de elementos: `límite_superior - límite_inferior + 1`.

Operaciones formales:
- **Asignación / lectura / escritura**: `V[i] := valor`, análogo a `lista[i] = valor` en Python.
- **Recorrido**: con `desde i = liminf hasta limsup` o `mientras`, igual que `for i in range(len(lista))`.
- **Actualización** (a diferencia de Python, no hay `append`/`insert`/`remove` nativos): añadir un elemento al final requiere una variable contador del último ocupado; **insertar** en una posición intermedia requiere desplazar manualmente todos los elementos posteriores una posición a la derecha; **borrar** requiere desplazar los siguientes una posición a la izquierda. Python encapsula estos desplazamientos dentro de `insert()`/`pop()`/`remove()`.

## Arrays bidimensionales (matrices)
Notación `M[fila, columna]`, declarado `array[1..F, 1..C] de <tipo>`. Se recorre típicamente con un bucle anidado (filas en el externo, columnas en el interno, o viceversa). Equivale conceptualmente a una "lista de listas" en Python (`matriz[i][j]`), aunque en Joyanes Aguilar se usa una única estructura con dos índices, no listas anidadas.

## Arrays multidimensionales
Generalización a n dimensiones: `array[1..D1, 1..D2, ..., 1..Dn] de <tipo>`. Ejemplos típicos: ocupación de asientos de un avión (fila × columna × vuelo), inscripciones universitarias (alumno × materia × cuatrimestre).

## Almacenamiento en memoria
Aunque un array se *piense* en N dimensiones, la memoria es lineal (direcciones consecutivas). El compilador traduce los índices a una única dirección con una fórmula, p. ej. para un vector: `dirección = base + (i - límite_inferior) * tamaño_elemento`. Para matrices hay dos convenciones de orden:
- **Orden por filas (row-major)**: se almacena fila tras fila — usado por C, C++, Pascal, COBOL.
- **Orden por columnas (column-major)**: se almacena columna tras columna — usado por FORTRAN.

El orden de almacenamiento no afecta el resultado de un algoritmo correcto, pero sí su **rendimiento** (acceder en el orden "natural" de almacenamiento es más eficiente por localidad de memoria).

## Arrays paralelos
Dos o más arrays de igual tamaño relacionados por un índice común (p. ej. `nombres[i]` y `edades[i]` describen a la misma persona en la posición `i`) — mismo concepto que "listas paralelas" ya documentado en [[conceptos/listas-python]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmo]]
- [[conceptos/estructuras-registros]]
