---
titulo: "Archivos (Ficheros)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [archivos, ficheros, almacenamiento-secundario, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Archivos (Ficheros)

Un **archivo** (fichero) es una colección de **registros** relacionados, almacenada de forma **permanente** (persistente) en un dispositivo de almacenamiento secundario (disco, etc.) — a diferencia de las [[conceptos/arrays-vectores-matrices|estructuras en memoria principal]] (arrays, variables), que desaparecen cuando termina el programa.

## Jerarquía de datos
```
bit → carácter (byte) → campo → registro → archivo → base de datos
```
- **Campo**: dato elemental (nombre, edad, etc.).
- **Registro**: colección de campos relacionados sobre una entidad (similar a una [[conceptos/estructuras-registros|estructura/registro]] — ambos almacenan datos heterogéneos). Tiene una **clave** que lo identifica unívocamente.
- **Archivo**: colección de registros del mismo tipo.
- **Base de datos**: colección de archivos relacionados.

## Terminología clave
- **Registro lógico**: la unidad de información tal como la ve el programador (campos).
- **Registro físico (bloque)**: la cantidad mínima de datos transferida en una operación de E/S entre memoria y disco. El **factor de bloqueo** es la cantidad de registros lógicos por bloque (afecta directamente al rendimiento: más registros por bloque = menos operaciones de E/S, pero más memoria intermedia/*buffer* requerida).
- **Soporte secuencial**: para llegar al registro *n* hay que pasar por los *n-1* anteriores.
- **Soporte direccionable** (ej. disco): cualquier registro se localiza directamente por su dirección.

## Organización de archivos
| Organización | Acceso | Característica |
|---|---|---|
| **Secuencial** | Solo secuencial | Registros uno tras otro; termina en marca EOF/FDA |
| **Directa (aleatoria)** | Directo, por índice o clave | Requiere soporte direccionable; usa función de conversión (*hash*) clave→dirección |
| **Secuencial indexada** | Híbrido (vía un índice) | Área de datos + área de índice + zona de desbordamiento — como el índice de un libro |

## Operaciones básicas de gestión
`crear`, `abrir` (modo lectura `l`, escritura `e`, o `l/e`), `cerrar`, `leer`, `escribir`, `borrar`. Sobre los registros: consulta, inserción (altas), borrado (bajas), modificación.

Una **baja lógica** marca el registro como inválido (bandera/campo `ocupado`) sin eliminarlo físicamente; una **baja física** lo elimina realmente (típicamente reescribiendo un archivo nuevo sin él).

## Archivos de texto vs. binarios
- **Texto** (extensión `.txt`): solo caracteres imprimibles; portable entre sistemas; requiere conversión carácter↔número al leer/escribir datos numéricos.
- **Binario** (extensión `.dat`): cualquier valor de byte; más compacto y sin conversión, pero no legible directamente ni fácilmente portable.

## Streams (flujos): C++/Java vs. Python
En C++ y Java, el acceso a archivos se modela mediante **flujos** (*streams*): un objeto que conecta el programa con una fuente/destino de bytes (`FileInputStream`, `BufferedReader` en Java; `fstream` en C++), con apertura/lectura-escritura/cierre explícitos. Python abstrae todo esto: `open(archivo, modo)` (modos `'r'`/`'w'`/`'a'`) devuelve un objeto archivo iterable línea a línea, y el patrón `with open(...) as f:` cierra el archivo automáticamente — equivalente conceptual a abrir+leer+cerrar pero sin gestionar el flujo manualmente.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/estructuras-registros]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/algoritmos-archivos]]
