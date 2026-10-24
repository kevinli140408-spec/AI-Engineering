---
titulo: "Sistemas de Numeración"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-10-24
tags: [hardware, sistemas-de-numeracion, binario]
fuentes: [arquitectura-computadoras-clase3-uade, arquitectura-computadoras-clase4-apunte-uade, arquitectura-computadoras-clase5-apunte-uade]
---

# Sistemas de Numeración

Desarrollo en profundidad de las bases numéricas usadas en computación: conversiones, aritmética y unidades. Complementa a [[conceptos/representacion-de-la-informacion]] (que cubre codificación de caracteres, enteros con signo y punto flotante) con el detalle de bases, algoritmos de conversión y aritmética binaria manual.

## Posicional vs. no posicional

Un sistema es **posicional** cuando el valor de un dígito depende de su posición (decimal, binario, octal, hex); es **no posicional** cuando no (ej. números romanos, donde cada símbolo vale siempre lo mismo).

## Bases usadas en computación

| Base | Nombre | Dígitos | Origen del uso |
|---|---|---|---|
| 2 | Binario | 0, 1 | Estados físicos del transistor (ver [[conceptos/semiconductores-y-transistores]]) |
| 8 | Octal | 0-7 | Agrupa bits de a 3 |
| 10 | Decimal | 0-9 | Uso humano estándar |
| 16 | Hexadecimal | 0-9, A-F | Agrupa bits de a 4 |

Octal y hexadecimal surgieron después de 1950 como notación abreviada para que los humanos manejen cadenas binarias largas sin perder equivalencia exacta con el binario.

## Unidades

**Bit** (unidad mínima) → **nibble** (4 bits) → **byte** (8 bits) → **palabra/word** (tamaño nativo de registro del procesador; varía por fabricante: 16/32/64 bits en Intel, 32/64 bits en Apple).

## Conversiones

- **Binario → decimal**: suma de potencias de 2 en las posiciones con 1 (ej. `1001₂ = 2³+2⁰ = 9₁₀`).
- **Decimal → binario**: restas sucesivas de potencias de 2 de mayor a menor (ej. `73₁₀ = 2⁶+2³+2⁰ = 1001001₂`).
- **Hexadecimal ↔ binario**: cada dígito hex equivale exactamente a 4 bits fijos (ej. `9F2₁₆ = 100111110010₂`); al convertir binario→hex se rellena con ceros a la izquierda hasta completar grupos de 4.
- **Binario ↔ octal**: agrupando de a 3 bits.
- **Octal ↔ hexadecimal**: no hay relación directa; se pasa por binario. Ej.: `13725₈ = 001 011 111 010 101₂ = 0001 0111 1101 0101₂ = 17D5₁₆` (el apunte original decía `1725`; ver [[fuentes/arquitectura-computadoras-clase4-apunte-uade]]).
- **Hexadecimal → decimal**: se recomienda pasar siempre por binario como paso intermedio, en vez de dividir directamente por 16.

## Aritmética binaria

- **Suma**: reglas `0+0=0`, `0+1=1`, `1+1=0 (acarreo 1)`, `1+1+1=1 (acarreo 1)`.
- **Resta**: cuando el minuendo es menor, se "pide prestado" (acarreo negativo) a la posición siguiente, análogo a la resta decimal.
- **Fracciones binarias**: la parte fraccionaria se representa con potencias negativas de 2 (`2⁻¹, 2⁻², ...`); ej. `20,8125₁₀ = 10100,1101₂`.

## Direccionamiento: bits vs. direcciones

Con n bits de dirección hay **2ⁿ direcciones** (no confundir n con 2ⁿ); sumar **un** bit duplica la cantidad (10 bits = 1024; 11 bits = 2048). Capacidad = direcciones × tamaño de palabra: una memoria de 512 bytes con 8 bits de dirección (256 direcciones) guarda 2 bytes por palabra. Ver [[conceptos/buses-de-sistema]] y [[fuentes/arquitectura-computadoras-clase5-apunte-uade]].

## Unidades de almacenamiento: KB vs. KiB

Uso comercial (discos, redes) suele usar prefijos decimales (KB=10³), mientras que el sistema operativo suele medir en potencias exactas de 2 (KiB=2¹⁰=1024) — la discrepancia explica por qué un disco de "1TB" muestra ~930GB reales. Ver tabla completa de unidades en [[conceptos/organizacion-de-computadoras]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase3-uade]]
- [[fuentes/arquitectura-computadoras-clase4-apunte-uade]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/semiconductores-y-transistores]]
- [[conceptos/organizacion-de-computadoras]]
