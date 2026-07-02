---
titulo: "Archivos (Ficheros)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-01
tags: [archivos, ficheros, almacenamiento-secundario, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
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

## El protocolo abrir → leer/escribir → cerrar en Python ([[fuentes/introduccion-a-la-programacion-con-python-3]])
```python
fichero = open('datos.txt')        # modo 'r' (lectura) por defecto
for linea in fichero:              # recorre línea a línea (incluye el '\n' final)
    print(linea.rstrip())
fichero.close()
```
Modos de apertura: `'r'` (lectura, falla con `IOError`/`FileNotFoundError` si no existe), `'w'` (escritura — **borra** el contenido previo si el fichero ya existía), `'a'` (adición, añade al final sin borrar), `'r+'`/similares (lectura/escritura combinada). Formas de leer:
- `for linea in fichero:` — la más habitual, recorre línea a línea sin cargar todo el fichero en memoria.
- `fichero.readline()` — lee una sola línea; devuelve cadena vacía `''` al llegar al final (condición de parada de un `while`).
- `fichero.read()` / `fichero.read(n)` — lee todo el fichero (o `n` caracteres) de una vez como una única cadena.
- `fichero.readlines()` — lee todo el fichero de una vez como lista de líneas.

Los tres últimos métodos cargan contenido íntegro en memoria: evitarlos con ficheros grandes. Para escribir: `fichero.write(cadena)` (no añade salto de línea automáticamente — hay que incluir `'\n'` explícitamente si se quiere).

### Persistencia de estructuras de datos: el módulo `pickle`
Guardar y recuperar una lista o un diccionario completo, dato a dato, es tedioso. El módulo `pickle` serializa cualquier estructura de datos Python directamente a un fichero binario y la reconstruye tal cual: `pickle.dump(lista, open('f.dat', 'wb'))` para guardar, `pickle.load(open('f.dat', 'rb'))` para recuperar. Es la forma más simple de que un programa "recuerde" información entre distintas ejecuciones sin diseñar un formato de texto propio.

### Por qué siempre hay que cerrar el fichero
Las lecturas/escrituras a disco pasan primero por un **buffer** en RAM (mucho más rápida que el disco); el contenido no se vuelca físicamente al disco hasta que el buffer se llena o el fichero se cierra. Un programa que termina sin cerrar un fichero corre el riesgo de perder los últimos cambios o corromper el fichero. `with open(...) as f:` es la forma recomendada precisamente porque garantiza el cierre incluso si ocurre una excepción a mitad de la operación.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/estructuras-registros]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/algoritmos-archivos]]
- [[conceptos/diccionarios-python]]
