---
titulo: "Archivos (Ficheros)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [archivos, ficheros, almacenamiento-secundario, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, programacion1-archivos-thompson]
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

### Modo de apertura en detalle y rutas de Windows
El modo de apertura combina un carácter básico (`r`/`w`/`a`) con un modificador opcional `t` (texto, el valor por defecto si se omite el modo completo: `open(archivo)` equivale a `"rt"`). En Windows, una ruta con barras invertidas simples puede chocar con secuencias de escape (`"c:\nuevo\datos.txt"` contiene un `\n` real, es decir un salto de línea, y produce una ruta inválida). Tres soluciones equivalentes: doble barra invertida (`"c:\\nuevo\\datos.txt"`), barra normal —Windows la acepta igual que `/` (`"c:/nuevo/datos.txt"`), o declarar la cadena como *raw* (`open(r"c:\nuevo\datos.txt", "wt")`).

### Patrón try/except/finally recomendado (sin `with`)
Como `open()` puede fallar por múltiples motivos (ruta inválida, archivo inexistente en modo `r`, disco lleno o protegido, permisos insuficientes, archivo ya abierto por otro proceso), la apertura debe ir siempre dentro de un bloque protegido — ver [[conceptos/manejo-de-excepciones]]. Encadenar excepciones de más específica a más genérica: primero `FileNotFoundError`, luego `OSError` (sinónimo `IOError`) como red de contención final. El cierre va en `finally`, envuelto a su vez en un `try`/`except NameError: pass` — porque si `open()` nunca llegó a asignar la variable (falló antes), intentar `arch.close()` lanzaría `NameError`:

```python
try:
    arch = open("alumnos.txt", "wt")
    # ... procesamiento ...
except FileNotFoundError as mensaje:
    print("No se puede abrir el archivo:", mensaje)
except OSError as mensaje:
    print("Error de E/S:", mensaje)
finally:
    try:
        arch.close()
    except NameError:
        pass
```

### Delimitador de línea y conversión de datos
Python graba `"\n"` como delimitador entre registros, pero el carácter físico depende del sistema operativo (Windows: CR+LF; Linux/Android: solo LF; macOS: solo CR) — a esta traducción automática se la llama **conversión de datos**, exclusiva de archivos de texto (no ocurre en binarios).

### Formato CSV sin módulos
Un archivo CSV (*comma-separated values*) es simplemente un archivo de texto donde cada línea tiene sus campos separados por un delimitador (coma, punto y coma, etc.); no hace falta `import csv` para leerlo o escribirlo a mano con `split()`/concatenación — el módulo estándar solo aporta comodidad extra (manejo de comillas, tipos de dato, etc.).

### Indicador de posición y `seek(0)`
El **indicador de posición** (o puntero de lectura/escritura) marca cuál es el próximo registro a leer o grabar, y avanza automáticamente con cada operación. Al terminar de leer un archivo, el indicador queda al final — volver a leerlo requiere `arch.seek(0)` (retrocede al comienzo) en vez de cerrar y reabrir el archivo (más costoso en recursos; solo se justifica si además cambia el modo de apertura).

### `for` sobre un archivo vs. métodos de lectura — no combinar
Un objeto archivo es iterable: `for linea in arch:` recorre línea por línea igual que `readline()` en un bucle, sin necesitar el método explícito. **No deben mezclarse** ambos enfoques en el mismo recorrido (alternar `for linea in arch:` con una llamada suelta a `arch.readline()`): cada uno avanza el indicador de posición de forma independiente, y combinarlos salta o pierde registros.

### Regla estricta contra cargar el archivo completo en memoria
Más allá de la recomendación general de evitar `read()`/`readlines()` con archivos grandes, esta cátedra la trata como una **prohibición absoluta**, equiparándola a un ciclo infinito por mala práctica — un archivo puede tener millones de registros. Esto también descarta patrones aparentemente inofensivos como acumular todas las líneas en una lista dentro de un `for`, o concatenarlas todas en una única cadena con un `while`.

### Codificación UTF-8 explícita
Si aparece `UnicodeDecodeError` al leer, o los caracteres regionales (`ñ`, tildes) se leen dañados, el archivo fue grabado en UTF-8 y debe abrirse indicándolo: `open("datos.txt", "rt", encoding="UTF8")`.

### Buenas prácticas adicionales
El nombre del archivo es una decisión del programador, no debe pedirse por teclado al usuario; el archivo se abre una sola vez, se procesa por completo y se cierra (nunca abrir/cerrar por cada registro); toda lectura o escritura debe operar sobre el **registro completo** (una línea), nunca campo por campo, por razones de eficiencia.

### Por qué siempre hay que cerrar el fichero
Las lecturas/escrituras a disco pasan primero por un **buffer** en RAM (mucho más rápida que el disco); el contenido no se vuelca físicamente al disco hasta que el buffer se llena o el fichero se cierra. Un programa que termina sin cerrar un fichero corre el riesgo de perder los últimos cambios o corromper el fichero. `with open(...) as f:` es la forma recomendada precisamente porque garantiza el cierre incluso si ocurre una excepción a mitad de la operación.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-archivos-thompson]]
- [[conceptos/estructuras-registros]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/algoritmos-archivos]]
- [[conceptos/diccionarios-python]]
- [[conceptos/manejo-de-excepciones]]
- [[conceptos/json]]
