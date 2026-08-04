---
titulo: "Subespacio Vectorial"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, espacios-vectoriales, subespacios]
fuentes: [espacios-vectoriales-uade]
---

# Subespacio Vectorial

Un subconjunto S de un [[conceptos/espacio-vectorial|espacio vectorial]] V es un **subespacio** si verifica:

1. 0 ∈ S (el vector nulo de V pertenece a S)
2. ∀ u ∈ S, ∀ α ∈ K: α·u ∈ S (cerrado bajo producto por escalar)
3. ∀ u,v ∈ S: u+v ∈ S (cerrado bajo suma)

Todo subespacio es en sí mismo un espacio vectorial (hereda las operaciones de V). {0_V} y V son siempre subespacios de V (los "triviales").

## Combinación lineal

Dado A = {v₁, v₂, …, v_m} ⊆ V y v ∈ V, v es **combinación lineal** de los elementos de A si existen escalares α₁,…,α_m tales que v = α₁v₁ + α₂v₂ + ⋯ + α_mv_m.

## Subespacio generado

Si A = {v₁,…,v_m} ⊆ V, el conjunto S de todas las combinaciones lineales de los elementos de A es un subespacio, llamado **subespacio generado** por A. Notación: S = gen{v₁,…,v_m}.

## Complemento ortogonal

Dado un subespacio S ⊆ V, su complemento ortogonal S⊥ = {v ∈ V : u⊥v, ∀u ∈ S} es también un subespacio de V, y cumple dim(S) + dim(S⊥) = dim(V).

## Ver también

[[conceptos/base-de-un-espacio-vectorial]] — independencia lineal, bases y coordenadas, construidas sobre estos conceptos.

## Referencias
- [[fuentes/espacios-vectoriales-uade]]
