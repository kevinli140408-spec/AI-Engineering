---
titulo: "Base de un Espacio Vectorial"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, espacios-vectoriales, base, coordenadas]
fuentes: [espacios-vectoriales-uade]
---

# Base de un Espacio Vectorial

## Dependencia e independencia lineal

Sea A = {v₁,…,v_m} un conjunto no vacío de vectores de un [[conceptos/espacio-vectorial|espacio vectorial]] V. La ecuación α₁v₁+α₂v₂+⋯+α_mv_m = 0 siempre tiene la solución trivial α₁=⋯=α_m=0. Si esa es la **única** solución, A es **linealmente independiente (LI)**; si existen otras soluciones, A es **linealmente dependiente (LD)**.

## Base

A es una **base** de un [[conceptos/subespacio-vectorial|subespacio]] S si: (1) A es linealmente independiente, y (2) A genera S (todo elemento de S es combinación lineal de A).

## Coordenadas de un vector en una base

Si B = {v₁,v₂} es base de un subespacio H y x = α₁v₁ + α₂v₂, el par (α₁,α₂) son las **coordenadas** de x en la base B, notado C_B(x) = (α₁,α₂). Cambiar de base cambia las coordenadas de un mismo vector — la [[conceptos/matriz-cambio-base|matriz de cambio de base]] formaliza esa conversión.

## Referencias
- [[fuentes/espacios-vectoriales-uade]]
- [[conceptos/subespacio-vectorial]]
