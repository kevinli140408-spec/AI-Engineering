---
titulo: "Matriz de Cambio de Base"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, cambio-de-base, transformaciones-lineales]
fuentes: [matriz-cambio-base-uade]
---

# Matriz de Cambio de Base

Sean B = {u₁,…,u_n} base de un [[conceptos/espacio-vectorial|espacio vectorial]] V y B' = {w₁,…,w_m} base de W. La **matriz de la transformación lineal T en las bases B, B'** tiene como columnas los transformados de los vectores de B, expresados en coordenadas de B':

M(T)_BB' = ( (T(u₁))_B'  (T(u₂))_B'  ⋯  (T(u_n))_B' )

**Propiedad**: para todo v ∈ V, (T(v))_B' = M(T)_BB' · (v)_B — la matriz convierte coordenadas en base B a coordenadas de T(v) en base B'.

## Caso particular: matriz de cambio de base

Sea T: Rⁿ → Rⁿ la [[conceptos/transformacion-lineal|transformación lineal]] identidad (T(v)=v), y B, B' dos bases de Rⁿ. Como (T(v))_B' = M(T)_BB'·(v)_B y T(v)=v, se obtiene (v)_B' = M(T)_BB'·(v)_B: la misma matriz M(T)_BB' convierte las [[conceptos/base-de-un-espacio-vectorial|coordenadas]] de un vector en la base B a sus coordenadas en la base B'. Para esta transformación identidad, M(T)_BB' se llama **matriz de cambio de base**, notada C(B,B').

## Referencias
- [[fuentes/matriz-cambio-base-uade]]
- [[conceptos/transformacion-lineal]]
- [[conceptos/base-de-un-espacio-vectorial]]
