---
titulo: "Matriz Inversa"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, matrices, matriz-inversa]
fuentes: [determinante-matriz-inversa-uade]
---

# Matriz Inversa

Sea A una [[conceptos/matriz|matriz cuadrada]] de orden n e I la matriz identidad de orden n. A es **inversible** si existe una matriz B de orden n tal que A·B = B·A = I. B se llama la inversa de A y se nota A⁻¹, de modo que A·A⁻¹ = A⁻¹·A = I.

Son equivalentes: "A es inversible", "A es regular" y "A es no singular".

## Condición de existencia

A es inversible **si y solo si** det(A) ≠ 0 (ver [[conceptos/determinante]]).

## Cálculo vía matriz adjunta

1. **Cofactor** c_ij = (-1)^(i+j)·det(M_ij) (M_ij: submatriz sin fila i ni columna j).
2. **Matriz de cofactores** Cof(A): matriz formada por todos los c_ij.
3. **Matriz adjunta**: adj(A) = [Cof(A)]ᵀ (traspuesta de la matriz de cofactores).
4. **Fórmula**: A⁻¹ = (1/det(A))·adj(A).

## Uso en sistemas de ecuaciones

Si un [[conceptos/sistema-de-ecuaciones-lineales|sistema]] cuadrado A·X = B tiene det(A) ≠ 0, la solución única se obtiene despejando: A⁻¹·(A·X) = A⁻¹·B → X = A⁻¹·B (método de la matriz inversa, alternativa al método de Gauss).

## Referencias
- [[fuentes/determinante-matriz-inversa-uade]]
- [[fuentes/sistemas-ecuaciones-lineales-uade]]
