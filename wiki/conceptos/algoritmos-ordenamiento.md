---
titulo: "Algoritmos de Ordenamiento"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [ordenamiento, algoritmos, listas, python]
fuentes: [orden-busqueda-mm]
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

## Referencias

- [[fuentes/orden-busqueda-mm]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmos-busqueda]]
