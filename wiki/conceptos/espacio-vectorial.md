---
titulo: "Espacio Vectorial"
tipo: concepto
creado: 2026-08-03
actualizado: 2026-08-03
tags: [algebra-lineal, espacios-vectoriales]
fuentes: [espacios-vectoriales-uade]
---

# Espacio Vectorial

Sea K un cuerpo de escalares (K=R o K=C) y V un conjunto no vacío ("vectores") con dos operaciones definidas: suma (+) y producto por un escalar (·). (V, +, K, ·) es un **espacio vectorial** si se verifican 10 axiomas:

**Cierre y suma** (∀ u,v,w ∈ V):
1. u+v ∈ V (cierre de la suma)
2. u+v = v+u (conmutativa)
3. (u+v)+w = u+(v+w) (asociativa)
4. ∃ 0 ∈ V: u+0 = 0+u = u (neutro)
5. ∀u ∈ V, ∃ -u ∈ V: u+(-u) = 0 (opuesto)

**Producto por escalar** (∀ u,v ∈ V, ∀ α,β ∈ K):
6. α·u ∈ V (cierre del producto)
7. (α+β)·u = α·u + β·u (distributiva en el escalar)
8. α·(u+v) = α·u + α·v (distributiva en el vector)
9. α·(β·u) = (α·β)·u (asociativa mixta)
10. ∃ 1 ∈ K: 1·u = u (neutro del producto)

Nótese el paralelo estructural con los axiomas de cuerpo que rigen los [[conceptos/numeros-reales|números reales]] y [[conceptos/numeros-complejos|complejos]] — un espacio vectorial generaliza la aritmética de esos cuerpos a objetos ("vectores") que no son necesariamente números.

## Relación con vectores geométricos

Los [[conceptos/vectores|vectores]] de R² y R³ vistos en el curso de geometría son el ejemplo canónico de espacio vectorial, pero la definición aquí es abstracta: cualquier conjunto que cumpla los 10 axiomas es un espacio vectorial (matrices de un tamaño fijo, polinomios de grado acotado, funciones, etc.).

## Estructura relacionada

Ver [[conceptos/subespacio-vectorial]] para subconjuntos de V que heredan la estructura de espacio vectorial, y [[conceptos/transformacion-lineal]] para funciones entre espacios vectoriales que preservan esta estructura.

## Referencias
- [[fuentes/espacios-vectoriales-uade]]
