---
titulo: "Validez de Razonamientos"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [logica, validez, razonamiento]
fuentes: [validez-razonamientos-mm]
---

# Validez de Razonamientos

Un [[conceptos/razonamiento]] es **válido** si sus premisas **implican lógicamente** su conclusión: no existe caso donde todas las premisas sean verdaderas y la conclusión falsa. Ver [[conceptos/relaciones-logicas]].

## Validez ≠ verdad

| Situación | ¿Posible en razonamiento válido? | ¿Posible en razonamiento inválido? |
|-----------|:---:|:---:|
| Premisas V, Conclusión V | ✓ | ✓ |
| Premisas V, Conclusión F | ✗ | ✓ |
| Premisas F, Conclusión V | ✓ | ✓ |
| Premisas F, Conclusión F | ✓ | ✓ |

La validez **no garantiza** que premisas ni conclusión sean verdaderas; garantiza que **si** las premisas son verdaderas, la conclusión **necesariamente** lo es.

## Métodos de evaluación

### 1. Tablas veritativas completas
1. Simbolizar el razonamiento.
2. Hacer la [[conceptos/tabla-de-verdad]] de premisas y conclusión.
3. Buscar renglón con todas las premisas V y conclusión F → si existe: **inválido**; si no: **válido**.

### 2. Técnica del condicional asociado
1. Simbolizar.
2. Formar `[P₁ • P₂ • ...] → C`.
3. Hacer tabla: **tautología** → válido; contingencia/contradicción → inválido.

### 3. [[conceptos/metodo-demostrativo|Método demostrativo]]
Usa reglas y leyes lógicas para derivar la conclusión paso a paso, sin tablas.

## Referencias

- [[fuentes/validez-razonamientos-mm]]
- [[conceptos/razonamiento]]
- [[conceptos/relaciones-logicas]]
- [[conceptos/metodo-demostrativo]]
