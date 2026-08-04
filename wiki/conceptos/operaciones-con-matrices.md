---
titulo: "Operaciones con Matrices"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, matrices, operaciones]
fuentes: [matrices-definiciones-operaciones-uade, determinante-matriz-inversa-uade]
---

# Operaciones con Matrices

## Producto de un escalar por una matriz

Sean A ∈ Rᵐˣⁿ y k ∈ R. El producto k·A ∈ Rᵐˣⁿ se obtiene multiplicando cada elemento de A por k. Es la única operación básica que la fuente de definiciones desarrolla explícitamente con ejemplo numérico.

## Producto de matrices (uso implícito)

No hay una definición formal dedicada en las diapositivas revisadas, pero es prerequisito para leer el resto del curso: [[conceptos/sistema-de-ecuaciones-lineales|A·X = B]], la condición de [[conceptos/matriz-inversa|matriz inversa]] (A·A⁻¹ = I) y [[conceptos/autovalores-autovectores|A·v = λ·v]] lo usan directamente. Regla estándar: (A·B)_ij = Σ_k a_ik·b_kj, válida solo si el número de columnas de A coincide con el número de filas de B. **Vacío de la fuente**: ni la suma ni el producto de matrices se definen formalmente en `matrices-definiciones-operaciones-uade`; aparecen solo implícitos en ejercicios (decodificación de un mensaje).

## Multiplicación por escalar y determinante

Relación entre esta operación y el [[conceptos/determinante]]: si A es de orden n, det(k·A) = kⁿ·det(A) — el escalar no se multiplica linealmente sino elevado a la potencia del orden de la matriz (propiedad 7 en [[fuentes/determinante-matriz-inversa-uade]]).

## Referencias
- [[fuentes/matrices-definiciones-operaciones-uade]]
- [[fuentes/determinante-matriz-inversa-uade]]
