---
titulo: "Computación Cuántica"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [computacion-cuantica, qubit, procesadores, seguridad]
fuentes: [arquitectura-computadoras-clase7-apunte-uade]
---

# Computación Cuántica

Tipo de procesador que opera con **qubits** en lugar de bits ([[conceptos/tipos-de-procesadores]]). Está en una etapa inicial de desarrollo.

## Lo que dice la clase

- La unidad de información es el **qubit**. Los procesadores deben operar cerca del cero absoluto (≈ −273 °C) para mantenerse estables.
- Empresas como IBM ya anunciaron avances (IBM Quantum). Se plantea como potenciador de la IA.
- **Riesgo de seguridad**: un procesador cuántico estable con muchos qubits podría romper los sistemas de cifrado actuales; la industria ya trabaja en nuevos sistemas basados en principios cuánticos.
- **Geopolítica**: competencia fuerte entre EE. UU. y China; los grandes avances suelen mantenerse en secreto hasta poder comercializarse ([[conceptos/geopolitica-de-semiconductores]]).
- **Acceso**: infraestructura extremadamente costosa, restringida a gobiernos y grandes corporaciones; no es una tecnología para el hogar a corto plazo. Se recomienda estudiar física como base.

## Precisiones (el propio apunte marca afirmaciones imprecisas)

| Afirmación de la clase | Más preciso |
|---|---|
| "Superposición = dos partículas toman el mismo estado" | Eso se parece más al **entrelazamiento**; la **superposición** es que un qubit puede estar en una combinación de 0 y 1 |
| "Millones de veces más rápido que cualquier computadora" | Solo vale para problemas específicos |
| "Un millón de qubits hackea cualquier banco en media hora" / "la seguridad desaparece en 5 años" | Son estimaciones. Amenazan sobre todo a **RSA y curvas elípticas** (algoritmo de Shor); AES-256 se debilita pero no se rompe |
| "100.000 qubits", "datos viajan 100.000 km en una décima de segundo" | No coinciden con las cifras públicas habituales |

Verificar estas cifras antes de citarlas en el TP.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
- [[conceptos/semiconductores-y-transistores]]
