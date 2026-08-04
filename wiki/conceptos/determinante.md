---
titulo: "Determinante"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, matrices, determinante]
fuentes: [determinante-matriz-inversa-uade]
---

# Determinante

Función que asigna a cada [[conceptos/matriz|matriz cuadrada]] A un número real, notado det(A) o |A|.

## Cálculo según el orden

- **Orden 1** (A=(a₁₁)): det(A) = a₁₁.
- **Orden 2**: det(A) = a₁₁·a₂₂ - a₁₂·a₂₁.
- **Orden 3 — Regla de Sarrus**: se repiten las dos primeras filas debajo de la matriz y se suman los productos de las tres diagonales descendentes, restando los productos de las tres diagonales ascendentes.
- **Orden n — Método de Laplace (cofactores)**: det(A) es la suma de los productos de los elementos de una fila (o columna) cualquiera por sus cofactores correspondientes. El **cofactor** c_ij = (-1)^(i+j)·det(M_ij), donde M_ij es la submatriz que resulta de eliminar la fila i y columna j de A.

## Propiedades (A, B matrices cuadradas de orden n)

1. Si una fila o columna es toda ceros, det(A) = 0.
2. Si A tiene dos filas o columnas iguales, det(A) = 0.
3. Si A tiene dos filas o columnas proporcionales, det(A) = 0.
4. Si A es [[conceptos/matriz|triangular]], det(A) = producto de la diagonal principal.
5. Intercambiar dos filas/columnas invierte el signo: det(B) = -det(A).
6. Multiplicar una fila/columna por k: det(B) = k·det(A).
7. Multiplicar toda la matriz por k: det(k·A) = kⁿ·det(A) — a diferencia de la propiedad 6, el escalar se eleva a la potencia n.
8. det(A·B) = det(A)·det(B).
9. det(Aᵀ) = det(A).
10. det(Aᵖ) = [det(A)]ᵖ.

## Rol en el curso

El determinante es la condición de existencia de la [[conceptos/matriz-inversa|matriz inversa]] (A es inversible ⟺ det(A) ≠ 0) y, vía el Teorema de Rouché-Frobenius y el [[conceptos/sistema-de-ecuaciones-lineales|método de la matriz inversa]], determina si un sistema cuadrado tiene solución única. También es la base del **polinomio característico** en [[conceptos/autovalores-autovectores]].

## Referencias
- [[fuentes/determinante-matriz-inversa-uade]]
