---
titulo: "Sistema de Ecuaciones Lineales"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, sistemas-de-ecuaciones]
fuentes: [sistemas-ecuaciones-lineales-uade]
---

# Sistema de Ecuaciones Lineales

Conjunto de m ecuaciones lineales con n incógnitas:

a₁₁x₁ + a₁₂x₂ + ⋯ + a₁ₙxₙ = b₁ ; … ; a_m1x₁ + ⋯ + a_mnxₙ = b_m

con a_ij, b_i ∈ R los coeficientes y términos independientes, x_j las incógnitas.

## Representación matricial

Equivalente a A·X = B, con A ∈ Rᵐˣⁿ (matriz de coeficientes), X ∈ Rⁿˣ¹ (incógnitas), B ∈ Rᵐˣ¹ (términos independientes). Si m ≠ n el sistema es **rectangular**; si m = n, **cuadrado**. Si B = 0 (todos los b_i = 0), el sistema es **homogéneo** (A·X = 0) y siempre es compatible (admite al menos la solución trivial X=0).

## Clasificación según cantidad de soluciones

- **Compatible determinado**: solución única.
- **Compatible indeterminado**: infinitas soluciones.
- **Incompatible**: sin solución.

## Rango de una matriz

Cantidad de filas no nulas de una matriz una vez triangulada (notación rg(A)).

## Teorema de Rouché-Frobenius

Un sistema es compatible si y solo si la matriz de coeficientes y la matriz ampliada tienen el mismo rango.

## Métodos de resolución

- **Método de Gauss**: se llevan sistemas a otros equivalentes (mismo conjunto solución) mediante operaciones elementales entre filas, hasta triangular la matriz.
- **Método de la matriz inversa**: si el sistema es cuadrado y A admite [[conceptos/matriz-inversa|inversa]] (det(A) ≠ 0), la solución única es X = A⁻¹·B.

## Aplicaciones trabajadas

Modelado de problemas de asignación de recursos (consumo de máquinas en una fábrica), presupuestos de viaje, y decodificación de mensajes mediante matrices.

## Referencias
- [[fuentes/sistemas-ecuaciones-lineales-uade]]
- [[conceptos/matriz-inversa]]
- [[conceptos/determinante]]
