---
titulo: "Representación de la Información"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-01
tags: [bits, codificacion, ascii, unicode, sistemas-de-numeracion]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Representación de la Información

Las computadoras solo entienden información descompuesta en **bits** (dígitos binarios: 0 o 1). Toda forma de información — texto, números, imágenes, sonido — se codifica como patrones de bits. Ver también [[conceptos/organizacion-de-computadoras]].

## Sistemas de numeración
| Sistema | Base | Dígitos |
|---|---|---|
| Decimal | 10 | 0-9 |
| Binario | 2 | 0, 1 |
| Octal | 8 | 0-7 |
| Hexadecimal | 16 | 0-9, A-F |

Ejemplo: 54 en decimal equivale a `00110110` en binario.

## Codificación de caracteres
- **ASCII** (American Standard Code for Information Interchange): 7 bits → 128 caracteres; ampliado a 8 bits → 256. El más usado históricamente.
- **Unicode**: 16 bits → 65.536 símbolos; soporta alfabetos no latinos (chino, árabe, etc.). Usado por lenguajes como Java. Mantenido por el consorcio Unicode (Apple, IBM, Microsoft, Oracle, entre otros); llamado a reemplazar a ASCII y a otros códigos regionales como Latin-1.
- **EBCDIC**: código de 8 bits, pionero de IBM, hoy en desuso.

> Las tablas completas de códigos ASCII (incluidos códigos de control y de teclado) están en el Apéndice C del libro — son datos de referencia (lookup), no contenido conceptual, por lo que no se vuelcan a una página propia del wiki.

## Representación de datos numéricos
- **Enteros**: notación binaria directa, con o sin signo; el rango depende del tamaño en bytes (p. ej. `int` de 4 bytes en C++: -2.147.483.648 a 2.147.483.647).
- **Reales**: notación en coma flotante (`N = M · B^E`, mantisa × base elevada al exponente), p. ej. `2.52e+8` equivale a 252.000.000.

Esto se conecta con los tipos de datos en programación — ver [[conceptos/variable-programacion]] (los tipos `int`/`float`/`str`/`bool` de Python equivalen conceptualmente a los tipos `int`/`float`-`double`/`char`/`bool` de C++ descritos aquí).

## Representación de imágenes y sonido
- **Imágenes**: mapas de bits (píxeles; formatos BMP/JPEG/GIF) o mapas de vectores (líneas, polígonos con atributos).
- **Sonido**: muestreo y digitalización de la señal analógica (p. ej. CD de audio: 44.000 muestras/segundo, 16 bits por muestra).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/variable-programacion]]
- [[conceptos/organizacion-de-computadoras]]
