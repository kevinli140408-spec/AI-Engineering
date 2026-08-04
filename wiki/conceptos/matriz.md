---
titulo: "Matriz"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, matrices]
fuentes: [matrices-definiciones-operaciones-uade]
---

# Matriz

Arreglo rectangular de números organizado en filas y columnas. Una matriz A de m filas y n columnas se nota A ∈ Rᵐˣⁿ, con elementos a_ij (fila i, columna j). Es el objeto central del álgebra lineal tal como se trabaja en este curso — no confundir con [[conceptos/arrays-vectores-matrices|el array bidimensional]] de estructuras de datos, que es la misma idea desde la óptica de la programación.

## Taxonomía según forma

- **Matriz cuadrada**: igual cantidad de filas y columnas (A ∈ Rⁿˣⁿ), se dice "de orden n".
- **Matriz fila**: orden 1×n.
- **Matriz columna**: orden m×1.
- **Matriz nula** (0): todos los elementos son 0, notación 0 ∈ Rᵐˣⁿ.

## Taxonomía en matrices cuadradas

- **Diagonal principal**: elementos a_ii (a₁₁, a₂₂, …, a_nn).
- **Traza**: tr(A) = a₁₁ + a₂₂ + ⋯ + a_nn, suma de la diagonal principal.
- **Triangular inferior**: a_ij = 0 si i < j (ceros arriba de la diagonal).
- **Triangular superior**: a_ij = 0 si i > j (ceros debajo de la diagonal).
- **Diagonal**: triangular superior e inferior a la vez (solo la diagonal puede ser no nula).
- **Identidad (I)**: matriz diagonal con todos los elementos de la diagonal iguales a 1; notación I ∈ Rⁿˣⁿ. Elemento neutro del producto matricial.
- **Simétrica**: a_ij = a_ji para todo i,j — equivalente a A = Aᵀ.
- **Antisimétrica**: a_ij = -a_ji para todo i,j — equivalente a A = -Aᵀ.

## Matriz traspuesta

Dada A ∈ Rᵐˣⁿ, la traspuesta Aᵀ ∈ Rⁿˣᵐ se obtiene intercambiando filas por columnas. Es la base de las definiciones de matriz simétrica/antisimétrica, y aparece en propiedades del [[conceptos/determinante|determinante]] (det(Aᵀ) = det(A)).

## Motivación de uso

En el curso, las matrices se introducen como herramienta de modelado: representar grafos/redes (matriz de adyacencia/pesos entre nodos) y tablas de datos (p. ej. contenido nutricional de alimentos), antes de tratarlas como objeto puramente algebraico.

## Operaciones

Ver [[conceptos/operaciones-con-matrices]].

## Referencias
- [[fuentes/matrices-definiciones-operaciones-uade]]
