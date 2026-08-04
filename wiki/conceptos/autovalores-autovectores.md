---
titulo: "Autovalores y Autovectores"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, autovalores, autovectores]
fuentes: [autovalores-autovectores-diagonalizacion-uade]
---

# Autovalores y Autovectores

Dada una [[conceptos/matriz|matriz cuadrada]] A de orden n, se buscan λ ∈ R y v ∈ Rⁿ (v ≠ 0) tales que A·v = λ·v. λ es un **autovalor** (eigenvalue) y v su **autovector** (eigenvector) asociado.

## Derivación y polinomio característico

A·v = λ·v ⟺ (A - λ·I_n)·v = 0. Si (A-λI_n) fuera inversible, la única solución sería v=0 — pero se busca v≠0, así que se exige det(A-λI_n) = 0. La función P(λ) = det(A-λ·I_n) es el **polinomio característico** de A; los autovalores son las raíces reales de P(λ)=0. El conjunto de autovalores de A es el **espectro** de A, notado σ(A).

## Autoespacio

Para cada autovalor λ, S_λ = {v ∈ Rⁿ : (A-λI_n)·v = 0} es un [[conceptos/subespacio-vectorial|subespacio]] de Rⁿ, llamado **autoespacio** asociado a λ — se obtiene resolviendo el [[conceptos/sistema-de-ecuaciones-lineales|sistema homogéneo]] (A-λI_n)v=0. Autovectores asociados a autovalores distintos son siempre linealmente independientes.

## Uso

Base para [[conceptos/diagonalizacion|diagonalizar]] una matriz.

## Referencias
- [[fuentes/autovalores-autovectores-diagonalizacion-uade]]
