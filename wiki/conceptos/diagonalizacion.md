---
titulo: "Diagonalización de Matrices"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, diagonalizacion, autovalores]
fuentes: [autovalores-autovectores-diagonalizacion-uade]
---

# Diagonalización de Matrices

Una matriz A ∈ Rⁿˣⁿ es **diagonalizable** si existe una matriz diagonal D ∈ Rⁿˣⁿ y una matriz inversible P ∈ Rⁿˣⁿ tales que P⁻¹·A·P = D.

## Condición

A es diagonalizable si y solo si, para cada [[conceptos/autovalores-autovectores|autovalor]] λ, la multiplicidad de λ como raíz del polinomio característico coincide con la dimensión del autoespacio S_λ asociado. Caso particular: si A tiene n autovalores distintos (n = orden de A), A es automáticamente diagonalizable — porque autovectores de autovalores distintos ya son linealmente independientes.

## Construcción de P y D

P se construye con los autovectores de A como columnas; D queda con los autovalores correspondientes en la diagonal, en el mismo orden que los autovectores en P.

## Referencias
- [[fuentes/autovalores-autovectores-diagonalizacion-uade]]
- [[conceptos/autovalores-autovectores]]
