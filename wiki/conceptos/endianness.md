---
titulo: "Endianness: Big Endian y Little Endian"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, endianness, direccionamiento, hexadecimal]
fuentes: [arquitectura-computadoras-clase5-apunte-uade, arquitectura-computadoras-clase8-apunte-uade]
---

# Endianness

Cuando un valor ocupa varios bytes y la memoria guarda 1 byte por celda, hay que decidir en qué **orden** se colocan. Lo define el procesador y el sistema operativo.

## Repaso de notación

El prefijo `0x` indica hexadecimal ([[conceptos/sistemas-de-numeracion]]). Un byte = 8 bits = 2 dígitos hexadecimales (cada uno es un nibble de 4 bits); separarlos de a dos muestra dónde termina un byte.

## Convenciones

| Convención | Qué se guarda primero (dirección más baja) |
|---|---|
| **Big Endian** | El byte más significativo (MSB) |
| **Little Endian** | El byte menos significativo (LSB) |

Ejemplo de la clase: `0x0A0B` en las direcciones 0 y 1 → Big: `0A 0B`; Little: `0B 0A`.

**Ejemplo adicional** (no figura en el apunte), con `0x12345678` en las direcciones 0 a 3: Big = `12 34 56 78`; Little = `78 56 34 12`.

## Según la arquitectura

| Arquitectura | Convención |
|---|---|
| x86 | Little Endian (estándar de la familia) |
| RISC / ARM | Variable: depende del fabricante y del diseño; ARM es configurable ([[entidades/arm]], [[conceptos/cisc-y-risc]]) |

## Por qué importa

Si un dato se guarda con una convención y se lee con la opuesta, el valor resultante es erróneo (basura). Hay que conocer el tipo de procesador al programar aplicaciones que acceden directamente a memoria o al intercambiar datos entre sistemas distintos. La Clase 5 ya mencionaba esta diferencia entre x86 y ARM ([[fuentes/arquitectura-computadoras-clase5-apunte-uade]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/jerarquia-y-clasificacion-de-memorias]]
