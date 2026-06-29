---
titulo: "Superficies Cilíndricas y Cuádricas"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [geometria, superficies, 3d]
fuentes: [superficies-uade]
---

# Superficies Cilíndricas y Cuádricas

Extensión tridimensional de las [[conceptos/conicas]]. Ecuaciones de segundo grado en tres variables.

## Superficies cilíndricas

Se generan al desplazar una curva plana (generatriz) a lo largo de una dirección fija. Característica: **la ecuación no involucra una de las tres variables**.

| Tipo | Generatriz | Ejemplo |
|------|-----------|---------|
| Cilindro parabólico | Parábola | z = x² (sin variable y) |
| Cilindro circular | Circunferencia | x² + y² = r² (sin variable z) |
| Cilindro elíptico | Elipse | x²/a² + y²/b² = 1 |

## Superficies cuádricas

Ecuaciones de segundo grado en x, y, z. Se analizan mediante **secciones** (cortes con planos).

| Superficie | Ecuación canónica | Secciones típicas |
|-----------|------------------|-------------------|
| Elipsoide | x²/a² + y²/b² + z²/c² = 1 | Elipses en los 3 planos |
| Paraboloide elíptico | z = x²/a² + y²/b² | Parábolas en xz, yz; elipses en z = k |
| Paraboloide hiperbólico | z = x²/a² − y²/b² | Parábolas en xz, yz; hipérbolas en z = k |
| Hiperboloide (1 hoja) | x²/a² + y²/b² − z²/c² = 1 | Elipses en z = k; hipérbolas en xz, yz |
| Hiperboloide (2 hojas) | −x²/a² − y²/b² + z²/c² = 1 | Elipses en z = k (|k| > c) |

## Método de análisis

1. Cortar con planos coordenados (xy, xz, yz)
2. Cortar con planos paralelos (z = k, y = k, x = k)
3. Identificar la curva de cada sección
4. Reconstruir la superficie 3D

## Referencias

- [[fuentes/superficies-uade]]
