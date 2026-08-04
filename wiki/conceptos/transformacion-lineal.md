---
titulo: "Transformación Lineal"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, transformaciones-lineales]
fuentes: [transformaciones-lineales-uade]
---

# Transformación Lineal

Sean V, W [[conceptos/espacio-vectorial|espacios vectoriales]]. Una función T: V → W es una **transformación lineal** si cumple:

i. ∀ u,v ∈ V: T(u+v) = T(u) + T(v)
ii. ∀ α ∈ K, ∀u ∈ V: T(α·u) = α·T(u)

Equivalente combinado: T(αu+βv) = αT(u) + βT(v). Consecuencia directa: T(0_V) = 0_W.

## Teorema fundamental de las transformaciones lineales

Dada una base B = {v₁,…,v_n} de V y cualquier conjunto de vectores {w₁,…,w_n} ⊂ W, existe una **única** transformación lineal T: V → W tal que T(v_i) = w_i para todo i. Consecuencia práctica: una transformación lineal queda completamente determinada por su efecto sobre una base — no hace falta especificarla vector por vector.

## Núcleo (kernel)

Nu(T) = {v ∈ V : T(v) = 0_W}. Es no vacío (0_V ∈ Nu(T) siempre) y es un [[conceptos/subespacio-vectorial|subespacio]] de V.

## Imagen

Im(T) = {w ∈ W : ∃ v ∈ V, T(v) = w} — subespacio de W.

## Teorema de la dimensión (rango-nulidad)

dim(Nu(T)) + dim(Im(T)) = dim(V).

## Referencias
- [[fuentes/transformaciones-lineales-uade]]
- [[conceptos/espacio-vectorial]]
- [[conceptos/matriz-cambio-base]]
