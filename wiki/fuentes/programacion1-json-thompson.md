---
titulo: "Programación I — Clase 9b: JSON"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, json, modulo-json]
---

# Programación I — Clase 9b: JSON

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Introducción a [[conceptos/json|JSON]] en Python vía el módulo `json`: serialización/deserialización, funciones `dumps`/`dump`/`loads`/`load`, límites de JSON como almacenamiento, y el formato JSON Lines.

## Contenido principal
- Concepto de JSON: formato de texto para intercambio entre sistemas, similar a XML; en Python se asocia típicamente a diccionarios.
- Serialización (objeto en memoria → texto) y deserialización (texto → objeto Python).
- `json.dumps(objeto)`: devuelve un string JSON; las claves de diccionario se convierten automáticamente a string.
- `json.dump(objeto, archivo)`: graba directamente en un archivo abierto.
- `json.loads(string)` y `json.load(archivo)`: decodificación desde string o desde archivo.
- Patrón de manejo de errores idéntico al de archivos: `try`/`except (FileNotFoundError, OSError)`/`finally` con cierre protegido.
- Advertencia: JSON no debe usarse como almacenamiento principal de grandes volúmenes de datos, porque se genera siempre desde datos completos en memoria.
- JSON Lines (JSONL): archivo de texto con un objeto JSON por línea, para procesar grandes volúmenes línea por línea sin cargar todo en memoria.

## Contraste con el resto de la wiki
Tema completamente nuevo — no existía página sobre JSON. Se creó [[conceptos/json]], enlazada desde [[conceptos/diccionarios-python]] (por la correspondencia natural dict↔JSON) y [[conceptos/archivos-ficheros]] (por el patrón de apertura/cierre compartido).

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/json]]
- [[conceptos/archivos-ficheros]]
