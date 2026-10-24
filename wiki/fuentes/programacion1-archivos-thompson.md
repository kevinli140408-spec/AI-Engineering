---
titulo: "Programación I — Clase 9: Archivos"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, archivos, ficheros]
---

# Programación I — Clase 9: Archivos

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Manejo de [[conceptos/archivos-ficheros|archivos]] de texto en Python: concepto de archivo/registro/campo, clasificación, las tres etapas (apertura/procesamiento/cierre), modos de apertura, métodos de lectura/escritura, delimitadores, indicador de posición, y reglas estrictas de la cátedra (sin `readlines()`, sin cargar el archivo en memoria).

## Contenido principal
- Por qué usar archivos: persistencia más allá de la memoria volátil; evolución tecnológica (tarjetas perforadas, cintas, discos, memorias no volátiles).
- Archivo = conjunto de registros; registro = conjunto de campos.
- Clasificación por sentido de transferencia (entrada/salida); archivos de texto = texto plano, extensión `.txt`.
- Delimitador `\n` entre registros y su conversión según sistema operativo (CR/LF).
- Las tres etapas: apertura (`open()`, modos `r`/`w`/`a` + `t`), procesamiento, cierre (`close()`).
- Rutas de Windows y el problema de `\n` en rutas: doble barra, barra normal, cadena raw.
- Manejo de excepciones alrededor de `open()`: `FileNotFoundError` antes de `OSError`/`IOError`; cierre en `finally` con `try/except NameError`.
- Métodos de escritura (`write`, `writelines`) y de lectura (`read`, `readline`) — `readlines()` explícitamente prohibido en la cátedra.
- Indicador de posición y `seek(0)` para releer sin cerrar/reabrir.
- `for linea in archivo:` como iterable, y la advertencia de no combinarlo con métodos de lectura explícitos.
- Copia de archivo transformando contenido (mayúsculas) usando `else`/`finally`.
- CSV sin necesidad de `import csv`; parámetro `encoding="UTF8"` para archivos con codificación UTF-8.
- Recomendaciones: no preguntar nombres de archivo al usuario, no abrir/cerrar por registro, operar siempre por registro completo (no por campo).

## Contraste con el resto de la wiki
[[conceptos/archivos-ficheros]] (originada en Joyanes Aguilar y Marzal et al.) ya cubría la teoría general de archivos y el patrón `open`/`for`/`close`, incluyendo `with`. Esta fuente aporta una variante de **estilo de cátedra más estricta**: no usa `with`, exige manejo explícito de excepciones alrededor de cada apertura/cierre, prohíbe expresamente cualquier forma de cargar el archivo completo en memoria (más allá de la recomendación general ya existente), y agrega detalle práctico nuevo — escaping de rutas de Windows, `seek(0)`, delimitador y su conversión por SO, y el parámetro `encoding`.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/archivos-ficheros]]
- [[conceptos/manejo-de-excepciones]]
