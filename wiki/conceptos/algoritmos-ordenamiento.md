---
titulo: "Algoritmos de Ordenamiento"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [ordenamiento, algoritmos, listas, python]
fuentes: [orden-busqueda-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
---

# Algoritmos de Ordenamiento

Procedimientos para reordenar los elementos de una [[conceptos/listas-python|lista]] (ej. de menor a mayor). Requieren la operación de **intercambio**, que usa una variable auxiliar:

```python
aux = lista[pos1]
lista[pos1] = lista[pos2]
lista[pos2] = aux
```

## Selección
Busca el **menor elemento** de toda la lista y lo intercambia con la primera posición; luego busca el segundo menor y lo intercambia con la segunda posición, y así sucesivamente.

```python
def metodoSeleccion(lista):
    for i in range(0, len(lista)-1):
        for j in range(i+1, len(lista)):
            if lista[i] > lista[j]:
                aux = lista[i]
                lista[i] = lista[j]
                lista[j] = aux
```

## Burbujeo
Compara **elementos consecutivos**, intercambiando si el primero es mayor que el segundo. El mayor "burbujea" hacia el final en cada pasada.

```python
def metodoBurbuja(lista):
    for recorrido in range(1, len(lista)):
        for i in range(len(lista) - recorrido):
            if lista[i] > lista[i+1]:
                aux = lista[i]
                lista[i] = lista[i+1]
                lista[i+1] = aux
```

**Burbujeo mejorado**: usa una bandera (`ordenado`) para detectar si ya no hubo intercambios en una pasada y así detener el ciclo antes de tiempo.

## Inserción
Va insertando cada elemento en su posición correcta dentro de la porción ya ordenada, **desplazando** (no intercambiando) los elementos mayores.

```python
def metodoInsercion(lista):
    for i in range(1, len(lista)):
        valorInsertar = lista[i]
        j = i
        while j > 0 and lista[j-1] > valorInsertar:
            lista[j] = lista[j-1]
            j = j - 1
        lista[j] = valorInsertar
```

## Ordenamientos especiales
Se puede ordenar según una **clave derivada** (no el valor directo) usando una función auxiliar que la calcule, por ejemplo, ordenar por valor absoluto ignorando el signo.

## Listas paralelas
Al ordenar una lista, si existe otra lista relacionada por subíndice (ej. legajos y notas), debe **reordenarse en paralelo** para mantener la correspondencia.

## Consideraciones
> "Ordenar listas es un proceso lento y costoso. Solo debe realizarse cuando sea estrictamente necesario."

## Métodos más avanzados (Joyanes Aguilar)
- **Shell**: mejora la inserción comparando elementos separados por un **salto** (`salto = N // 2`, reduciéndose a la mitad en cada pasada hasta llegar a 1), en lugar de elementos contiguos. Reduce drásticamente los desplazamientos largos típicos de la inserción simple en listas grandes.
- **Quicksort (ordenación rápida)**: usa la estrategia **"divide y vencerás"**. Se elige un **pivote**, se reordena el vector de modo que los menores queden a su izquierda y los mayores a su derecha (partición), y se aplica el mismo proceso recursivamente a cada mitad. Es, en promedio, el método más rápido de los vistos — base del algoritmo `sorted()`/`list.sort()` de muchos lenguajes (aunque Python usa *Timsort*, un híbrido de inserción y *merge sort*).
- **Mergesort (Cap. 14)**: versión recursiva de la [[conceptos/intercalacion|intercalación]] aplicada como método de ordenamiento completo: divide el vector por la mitad recursivamente hasta sublistas de un elemento (caso base, trivialmente ordenadas), y va mezclando los resultados al volver de cada llamada — el mismo patrón "divide y vencerás" de quicksort, pero dividiendo siempre por posición central en vez de por pivote. Tanto quicksort como mergesort son, en esencia, [[conceptos/recursividad|algoritmos recursivos]]: ver también el caso clásico de [[conceptos/torres-de-hanoi]] como ejemplo de recursión "divide y vencerás" en estado puro.

## Referencias

- [[fuentes/orden-busqueda-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/intercalacion]]
