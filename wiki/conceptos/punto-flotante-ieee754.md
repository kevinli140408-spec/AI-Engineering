---
titulo: "Punto Flotante IEEE 754"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-09-15
tags: [punto-flotante, ieee-754, representacion]
fuentes: [arquitectura-computadoras-clase4-uade, introduccion-a-la-programacion-con-python-3]
---

# Punto Flotante IEEE 754

Estándar para representar números reales en binario. Consolida y amplía la sección de coma flotante de [[conceptos/representacion-de-la-informacion]].

## Formatos

| Formato | Total | Signo | Exponente | Mantisa | Bias |
|---|---|---|---|---|---|
| **Float** (simple precisión) | 32 bits | 1 | 8 | 23 | 127 |
| **Double** (doble precisión) | 64 bits | 1 | 11 | 52 | 1023 |

## Interpretación (float de 32 bits)

`Valor = ± 2^(E−127) × 1,M`

- **Signo**: 1 bit (1 = negativo).
- **Exponente E**: 8 bits en [[conceptos/representacion-numeros-enteros|representación en exceso]] 127 — así se codifican exponentes negativos sin bit de signo ni complementos, y comparar dos floats se reduce casi a comparar sus bits.
- **Mantisa M**: 23 bits fraccionarios; el 1 entero está implícito (normalización `1,M`), regalando un bit de precisión.

### Ejemplo (de la fuente)
`1 | 10000001 | 10100000...` → signo −, E = 129 → 2^(129−127) = 2² = 4, M → 1,101₂ = 1 + 0,5 + 0,125 = 1,625 → **−4 × 1,625 = −6,5**.

## Limitaciones prácticas

No todo decimal tiene representación binaria exacta (`0.1` es una aproximación), lo que produce errores de redondeo — detalle y alternativas (`Decimal`, `Fraction`) en [[conceptos/representacion-de-la-informacion]].

Cuando un valor excede el formato de destino hay **desborde**: el caso del **Ariane 5** (float64 convertido a int16) citado en [[conceptos/flags-del-procesador]] es el ejemplo clásico.

## Referencias
- [[fuentes/arquitectura-computadoras-clase4-uade]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/representacion-numeros-enteros]]
