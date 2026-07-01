---
titulo: "Intercalación (Merge)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [intercalacion, merge, algoritmos, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Intercalación (Merge)

La **intercalación** es el proceso de combinar dos vectores **ya ordenados** en un único vector ordenado, sin necesidad de volver a ordenar todo desde cero.

## Idea
Dados dos vectores ordenados `A` (M elementos) y `B` (N elementos), se recorren ambos simultáneamente con dos índices `i`, `j`, comparando `A[i]` con `B[j]` en cada paso: el menor de los dos se copia al vector resultado `C` y se avanza su índice. Cuando uno de los vectores se agota, el resto del otro se copia directamente al final de `C` (ya está ordenado).

```
i ← 1; j ← 1; k ← 0
mientras (i <= M) y (j <= N) hacer
  k ← k + 1
  si A[i] < B[j] entonces
    C[k] ← A[i]; i ← i + 1
  si_no
    C[k] ← B[j]; j ← j + 1
  fin_si
fin_mientras
// copiar el resto del vector no agotado
```

Equivalente conceptual en Python (aunque `sorted(a + b)` resuelve el problema de forma directa, sin aprovechar que ambas listas ya están ordenadas):
```python
def intercalar(a, b):
    c, i, j = [], 0, 0
    while i < len(a) and j < len(b):
        if a[i] < b[j]:
            c.append(a[i]); i += 1
        else:
            c.append(b[j]); j += 1
    c.extend(a[i:])
    c.extend(b[j:])
    return c
```

## Costo
El vector resultado tiene `M + N` elementos y el algoritmo realiza como máximo `M + N - 1` comparaciones — mucho más eficiente que volcar ambos vectores juntos y volver a [[conceptos/algoritmos-ordenamiento|ordenarlos]] desde cero.

## Relación con otros algoritmos
- Es la operación central del **merge sort** (ordenamiento por mezcla): se divide recursivamente un vector por la mitad hasta sublistas de un elemento (trivialmente ordenadas) y se van intercalando de a pares — la misma estrategia "divide y vencerás" que [[conceptos/algoritmos-ordenamiento|quicksort]], pero dividiendo por posición fija en vez de por un pivote.
- Se generaliza a archivos (fusión externa de archivos secuenciales ordenados, usando una "ventana" en vez de un índice): ver [[conceptos/ordenacion-externa]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/algoritmos-archivos]]
- [[conceptos/ordenacion-externa]]
