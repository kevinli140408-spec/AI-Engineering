---
titulo: "Números Complejos"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [algebra, numeros-complejos]
fuentes: [complejos-uade]
---

# Números Complejos

Extensión de los [[conceptos/numeros-reales]] que permite resolver ecuaciones sin solución real (como x² + 1 = 0). Conjunto ℂ.

## Definición

z = a + bi, donde:
- **a = Re(z)**: parte real
- **b = Im(z)**: parte imaginaria
- **i**: unidad imaginaria, i² = −1

Se representan como puntos en el **plano complejo** (eje horizontal = real, vertical = imaginario).

## Conjugado

z̄ = a − bi. Propiedad clave: z · z̄ = a² + b² = |z|² (siempre real y no negativo).

## Operaciones

| Operación | Fórmula |
|-----------|---------|
| Suma | (a+bi) + (c+di) = (a+c) + (b+d)i |
| Producto | (a+bi)(c+di) = (ac−bd) + (ad+bc)i |
| División | z/w = z·w̄ / |w|² |

## Módulo y argumento

- **Módulo**: |z| = √(a² + b²) — distancia al origen
- **Argumento**: θ = arg(z) — ángulo con el eje real positivo

## Formas de representación

1. **Binómica**: a + bi
2. **Trigonométrica**: |z|·(cos θ + i·sin θ)
3. **Exponencial**: |z|·e^(iθ)

## Potenciación y radicación

- **De Moivre**: zⁿ = |z|ⁿ · (cos(nθ) + i·sin(nθ))
- **Raíces n-ésimas**: n soluciones equiespaciadas angularmente (separadas por 2π/n)

## Referencias

- [[fuentes/complejos-uade]]
- Aplicación directa en: [[conceptos/polinomios]] (teorema fundamental del álgebra)
