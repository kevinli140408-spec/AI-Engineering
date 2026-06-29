---
titulo: "Planos"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [geometria, planos, algebra-lineal]
fuentes: [planos-uade]
---

# Planos

Objeto geométrico bidimensional en ℝ³, definido por un punto y dos [[conceptos/vectores]] directores no paralelos, o por un punto y un vector normal.

## Determinación

Tres puntos no colineales definen un único plano.

## Ecuaciones

| Forma | Ecuación |
|-------|----------|
| Vectorial | P = P₀ + s·v₁ + t·v₂ |
| Normal/cartesiana | ax + by + cz = d |

En la forma normal, **n = (a, b, c)** es el vector perpendicular al plano.

## Posiciones relativas entre planos

| Posición | Condición |
|----------|-----------|
| Paralelos | n₁ ∥ n₂ (normales paralelas, d distintos) |
| Coincidentes | n₁ ∥ n₂ y misma ecuación |
| Secantes | n₁ no ∥ n₂ → se cortan en una [[conceptos/rectas|recta]] |
| Perpendiculares | n₁ · n₂ = 0 |

## Posiciones relativas recta-plano

| Posición | Condición |
|----------|-----------|
| Contenida | v ⊥ n y P₀ en el plano |
| Paralela | v ⊥ n y P₀ fuera del plano |
| Secante | v no ⊥ n → un punto de intersección |
| Ortogonal | v ∥ n |

## Intersecciones

- **Plano-plano**: resolver sistema de 2 ecuaciones → recta paramétrica
- **Recta-plano**: sustituir paramétrica en ecuación del plano → resolver t

## Distancia punto-plano

Se calcula mediante proyección ortogonal del punto sobre el plano.

## Referencias

- [[fuentes/planos-uade]]
