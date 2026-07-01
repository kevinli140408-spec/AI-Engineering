---
titulo: "Ordenación Externa: Partición y Fusión de Archivos"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [ordenacion-externa, archivos, particion, fusion, mezcla, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Ordenación Externa: Partición y Fusión de Archivos

Cuando un [[conceptos/archivos-ficheros|archivo]] es demasiado grande para caber en memoria central, los algoritmos de [[conceptos/algoritmos-ordenamiento|ordenamiento interno]] (selección, burbujeo, quicksort, etc.) no se pueden aplicar directamente. La **ordenación externa** resuelve esto combinando dos operaciones: **partición** (dividir un archivo en varios) y **fusión** (combinarlos de nuevo, ya ordenados).

## Fusión de archivos
Es la versión "en disco" de la [[conceptos/intercalacion|intercalación]]: en vez de índices sobre un vector en memoria, se usa una **ventana** — una variable que mantiene visible el registro "actual" de cada archivo de entrada, ya que un archivo secuencial solo permite leer un registro a la vez. Se comparan las ventanas de F1 y F2, se escribe la menor al archivo resultado y se avanza (lee el siguiente registro) en el archivo de donde salió. Cuando un archivo se agota, el resto del otro se copia tal cual (ya está ordenado).

## Partición de archivos
Dividir un archivo en dos o más, según distintos criterios:
- **Clasificación interna**: leer un bloque de M registros que sí entra en memoria, ordenarlo internamente, y escribirlo como una partición (secuencia ordenada).
- **Por contenido**: separar registros según si un campo coincide con un valor `v` (p. ej., separar por categoría).
- **Selección por sustitución**: aprovecha el orden parcial que ya pueda tener el archivo original — usa un indicador de "congelado" para no volver a seleccionar en la misma pasada un registro menor al último emitido, generando particiones (tramos ordenados) más largas que el tamaño de la memoria disponible.
- **Por secuencias**: alterna registros (o bloques de longitud fija) entre dos archivos de salida, de forma puramente posicional (par/impar), sin mirar el contenido.

## Clasificación externa (ordenar un archivo completo)
Si el archivo cabe en memoria: se lee completo, se ordena con un algoritmo interno y se reescribe. Si no cabe, se combina partición + fusión repetidamente:

- **Mezcla directa**: se particiona el archivo en secuencias de longitud 1 (cada registro es, trivialmente, una secuencia ordenada), se funden en pares para obtener secuencias de longitud 2, se vuelve a particionar y fundir duplicando la longitud en cada pasada (1→2→4→8...) hasta que una sola secuencia cubra todo el archivo.
- **Mezcla natural**: en vez de partir siempre en secuencias de longitud 1, aprovecha los tramos *ya ordenados* (de longitud variable) presentes en el archivo original — esto reduce el número de pasadas necesarias frente a la mezcla directa.
- **Mezcla de secuencias equilibradas**: variante que usa 4 archivos de trabajo (F1-F4) en vez de 2, repartiendo las secuencias alternadamente entre un par de ellos en cada fase, duplicando el tamaño de secuencia en cada pasada — reduce la cantidad de E/S frente a usar solo 2 archivos de trabajo.

## Archivos ordenados por clave jerárquica
Un archivo puede ordenarse por una **clave primaria** y, dentro de ella, por **claves secundarias** (C1, C2, ..., Cn) en orden jerárquico — el mismo concepto de ordenamiento multi-criterio, aplicado a registros de archivo. Los sistemas operativos suelen ofrecer utilidades de `SORT` que implementan estos algoritmos sin que el programador deba escribirlos.

## Equivalente práctico en Python
Para archivos que caben en memoria, `sorted()` sobre las líneas leídas resuelve el problema directamente. Para archivos verdaderamente grandes, Python no tiene un mezclador externo incorporado de uso directo, pero el módulo `heapq.merge()` implementa la misma idea que la fusión descrita arriba: combina varios iterables ya ordenados (p. ej., archivos abiertos línea a línea) en un único flujo ordenado, sin cargar todo en memoria a la vez.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/intercalacion]]
- [[conceptos/algoritmos-archivos]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/archivos-ficheros]]
