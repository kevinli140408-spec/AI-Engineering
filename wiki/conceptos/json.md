---
titulo: "JSON (JavaScript Object Notation)"
tipo: concepto
creado: 2026-09-09
actualizado: 2026-09-09
tags: [json, python, modulo-json, serializacion, jsonl]
fuentes: [programacion1-json-thompson]
---

# JSON (JavaScript Object Notation)

**JSON** es un formato basado en texto para almacenar e intercambiar información entre sistemas heterogéneos, similar en propósito al estándar XML. En Python se trabaja habitualmente con [[conceptos/diccionarios-python|diccionarios]] (aunque admite otros tipos: listas, números, cadenas, booleanos), y todas las funciones para manipularlo están en el módulo estándar `json`.

## Serialización y deserialización
- **Serialización**: convertir un objeto en memoria (p. ej. un diccionario) a una secuencia de caracteres transferible (a un archivo o por red).
- **Deserialización**: el proceso inverso, decodificar un flujo JSON de vuelta a datos utilizables en Python.

## Codificación: `dumps()` y `dump()`

```python
import json

alumnos = {
    1000000: {"nombre": "Martin Fernandez", "promedio": 7.65},
    1000001: {"nombre": "Melina Gallo", "promedio": 8.91},
}

datos = json.dumps(alumnos)   # → string JSON, en memoria
print(datos)
# {"1000000": {"nombre": "Martin Fernandez", "promedio": 7.65}, ...}
```

`json.dumps(objeto)` devuelve un `string`. **Importante**: las claves del diccionario se transforman automáticamente en cadenas (`1000000` → `"1000000"`) en el resultado JSON, aunque en el diccionario Python original fueran enteros.

`json.dump(objeto, archivo)` hace lo mismo pero graba directamente en un archivo abierto, en vez de devolver un string:

```python
try:
    arch = open("datos.json", "wt")
    json.dump(alumnos, arch)
except (FileNotFoundError, OSError) as error:
    print("ERROR DE GRABACION:", error)
finally:
    try:
        arch.close()
    except NameError:
        pass
```

## Decodificación: `loads()` y `load()`
`json.loads(string)` convierte un string JSON en una variable Python (típicamente un diccionario); `json.load(archivo)` hace lo mismo leyendo directamente desde un archivo abierto:

```python
alumnos = json.loads(datos)          # desde un string
# o bien
arch = open("datos.json", "rt")
alumnos = json.load(arch)            # desde un archivo
```

El patrón de manejo de errores (`try`/`except (FileNotFoundError, OSError)`/`finally` con cierre protegido) es el mismo que para cualquier [[conceptos/archivos-ficheros|archivo]] — ver [[conceptos/manejo-de-excepciones]].

## Límite de JSON como almacenamiento
Un archivo JSON se genera siempre a partir de datos que ya están completos en memoria, lo que limita su escalabilidad. **No debe usarse como almacenamiento principal** de un sistema con grandes volúmenes de datos — no fue diseñado para eso.

## JSON Lines (JSONL)
Para manejar grandes cantidades de datos estructurados sin la limitación anterior, existe el formato **JSON Lines**: un archivo de texto donde **cada línea es un objeto JSON independiente** (un diccionario, lista, etc.), en vez de un único objeto JSON gigante para todo el archivo. Esto permite procesar el archivo línea por línea (como cualquier archivo de texto — ver [[conceptos/archivos-ficheros]]) sin cargarlo entero en memoria, aplicando `json.loads()` a cada línea individualmente:

```
{"nombre": "Juan Pérez", "edad": 30, "ciudad": "Mendoza"}
{"nombre": "Mia Sandoval", "edad": 25, "ciudad": "Trelew"}
```

## Referencias

- [[fuentes/programacion1-json-thompson]]
- [[entidades/python]]
- [[conceptos/diccionarios-python]]
- [[conceptos/archivos-ficheros]]
- [[conceptos/manejo-de-excepciones]]
