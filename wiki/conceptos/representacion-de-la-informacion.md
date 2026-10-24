---
titulo: "Representación de la Información"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-15
tags: [bits, codificacion, ascii, unicode, sistemas-de-numeracion]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3, arquitectura-computadoras-clase3-uade, arquitectura-computadoras-clase4-uade]
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

Ejemplo: 54 en decimal equivale a `00110110` en binario. Desarrollo completo de algoritmos de conversión entre bases, aritmética binaria y unidades (bit/nibble/byte/palabra) en [[conceptos/sistemas-de-numeracion]].

## Codificación de caracteres
- **ASCII** (American Standard Code for Information Interchange): 7 bits → 128 caracteres; ampliado a 8 bits → 256. El más usado históricamente.
- **Unicode**: estándar de *code points* que indexa todos los caracteres posibles (idiomas, emoji), mantenido por el UTC (Unicode Technical Committee); llamado a reemplazar a ASCII y a otros códigos regionales como Latin-1. **UTF-8** es su codificación más usada: 1 a 4 bytes por carácter, compatible con ASCII ([[fuentes/arquitectura-computadoras-clase4-uade]]).
- **EBCDIC**: código de 8 bits, pionero de IBM, hoy en desuso.

> Las tablas completas de códigos ASCII (incluidos códigos de control y de teclado) están en el Apéndice C del libro — son datos de referencia (lookup), no contenido conceptual, por lo que no se vuelcan a una página propia del wiki.

## Representación de datos numéricos
- **Enteros**: notación binaria directa, con o sin signo; el rango depende del tamaño en bytes (p. ej. `int` de 4 bytes en C++: -2.147.483.648 a 2.147.483.647).
- **Reales**: notación en coma flotante (`N = M · B^E`, mantisa × base elevada al exponente), p. ej. `2.52e+8` equivale a 252.000.000.

### IEEE 754 (coma flotante en Python)
Los flotantes de Python siguen el estándar **IEEE 754 de doble precisión** (64 bits: 1 bit de signo, 11 de exponente, 52 de mantisa), con base 2 y mantisa normalizada en `[1, 2)` ([[fuentes/introduccion-a-la-programacion-con-python-3]]). Consecuencia práctica: no todos los números decimales tienen representación exacta en binario (`0.1` es en realidad una aproximación infinitesimal, no el valor exacto), lo que puede producir pequeños errores de redondeo en cálculos encadenados. Para casos donde la precisión decimal exacta importa (p. ej. dinero) existen alternativas como el tipo `Decimal` (módulo `decimal`) o `Fraction` (numerador/denominador exacto), ambos más lentos que `float` pero exactos.

### Codificación de enteros con signo
Desarrollo completo con rangos por sistema (BSS, MyS, Ca1, Ca2, exceso) y ejercicios en [[conceptos/representacion-numeros-enteros]]; formato de coma flotante en detalle en [[conceptos/punto-flotante-ieee754]]. Tres formas de representar cantidades negativas con bits ([[fuentes/introduccion-a-la-programacion-con-python-3]]):
- **Signo-magnitud**: el bit más significativo indica el signo (0 = positivo, 1 = negativo) y el resto codifica la magnitud. Intuitivo, pero la suma de positivos y negativos es complicada de implementar en circuitería.
- **Complemento a uno**: para un número negativo se invierten todos los bits de su representación positiva. La suma es la convencional, pero si hay desbordamiento hay que sumarle 1 al resultado. Desventaja: el cero tiene dos representaciones (`00000000` y `11111111`), por lo que con 8 bits solo se representan 255 valores en vez de 256.
- **Complemento a dos** (la usada en los computadores reales): para cambiar el signo se invierten todos los bits y se suma 1. Ventajas: una única representación del cero y una sola operación de suma basta siempre, ignorando el bit desbordado. Rango con 8 bits: [-128, 127].

Ejemplo con 8 bits en complemento a dos: sumar 3 + (−2) da como resultado (tras descartar el bit de acarreo desbordado) el valor correcto 1.

Esto se conecta con los tipos de datos en programación — ver [[conceptos/variable-programacion]] (los tipos `int`/`float`/`str`/`bool` de Python equivalen conceptualmente a los tipos `int`/`float`-`double`/`char`/`bool` de C++ descritos aquí).

## Representación de imágenes y sonido
- **Imágenes**: mapas de bits (píxeles; formatos BMP/JPEG/GIF) o mapas de vectores (líneas, polígonos con atributos).
- **Sonido**: muestreo y digitalización de la señal analógica (p. ej. CD de audio: 44.000 muestras/segundo, 16 bits por muestra).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/arquitectura-computadoras-clase3-uade]]
- [[conceptos/variable-programacion]]
- [[conceptos/organizacion-de-computadoras]]
- [[conceptos/sistemas-de-numeracion]]
