---
titulo: "Polinomios"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [algebra, polinomios]
fuentes: [polinomios-uade]
---

# Polinomios

Expresiones de la forma P(x) = aₙxⁿ + aₙ₋₁xⁿ⁻¹ + ... + a₁x + a₀, donde n es el grado y aₙ es el coeficiente principal.

## Operaciones

- **Suma/resta**: se suman coeficientes de igual grado
- **Multiplicación**: distributiva, el grado del producto es la suma de grados
- **División**: algoritmo de división larga → P(x) = Q(x)·D(x) + R(x), con grado(R) < grado(D)

## Teoremas fundamentales

### Teorema del resto
El resto de dividir P(x) por (x − c) es P(c).

### Teorema del factor
(x − c) es factor de P(x) ⟺ P(c) = 0 (c es raíz de P).

### Teorema fundamental del álgebra
Todo polinomio de grado n con coeficientes en ℂ tiene **exactamente n raíces complejas** (contadas con multiplicidad). Conecta directamente con [[conceptos/numeros-complejos]].

## Raíces múltiples

Una raíz c tiene **multiplicidad k** si (x − c)ᵏ divide a P(x) pero (x − c)ᵏ⁺¹ no.

Comportamiento gráfico:
- **Multiplicidad par**: el gráfico toca el eje x sin cruzarlo
- **Multiplicidad impar**: el gráfico cruza el eje x

El **signo del coeficiente principal** determina el comportamiento en los extremos (positivo: sube a la derecha; negativo: baja).

## Referencias

- [[fuentes/polinomios-uade]]
