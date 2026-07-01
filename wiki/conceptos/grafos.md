---
titulo: "Grafos"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [grafos, estructuras-no-lineales, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Grafos

Un **grafo** generaliza el [[conceptos/arboles|árbol]] eliminando sus restricciones: un nodo puede conectarse con cualquier cantidad de otros nodos (no solo 2), y puede ser apuntado por más de uno. Formalmente, `G = {V, E}`: un conjunto de **vértices** (nodos) y un conjunto de **aristas/arcos** (líneas que unen pares de vértices). Modela redes reales: carreteras, vuelos, relaciones sociales.

## Terminología
- **Orden** del grafo: número de vértices.
- **Camino**: secuencia de arcos que conecta dos nodos; su **longitud** es el número de arcos que recorre.
- **Adyacencia**: dos vértices son adyacentes si un arco los une directamente.
- **Grafo dirigido** (dígrafo): los arcos tienen sentido (A→B no implica B→A). **No dirigido**: la relación es simétrica.
- **Grafo ponderado** (con peso): cada arista tiene un valor asociado (distancia, costo, capacidad) — base para problemas de camino más corto (p. ej. el [[conceptos/algoritmo-de-dijkstra|algoritmo de Dijkstra]]).
- **Grafo sencillo**: sin bucles (arco de un nodo a sí mismo) y sin arcos repetidos entre el mismo par; si no cumple esto, es **múltiple**.
- **Grafo conectado**: existe un camino entre cualquier par de vértices. **Desconectado**: hay vértices inalcanzables entre sí.
- **Grafo completo**: cada vértice está conectado con todos los demás (`n(n-1)` arcos dirigidos, o `n(n-1)/2` aristas no dirigidas).
- **Grafo disperso vs. denso**: según si el número de aristas es mucho menor o se acerca al máximo posible — determina qué representación conviene.

## Representación
- **Matriz de adyacencia**: array N×N donde `M[i][j] = 1` si hay arco de `i` a `j` (0 si no). Simple y rápida para consultar si dos nodos están conectados, pero desperdicia memoria en grafos dispersos (mayoría de ceros). Si el grafo no es dirigido, la matriz es simétrica.
- **Lista de adyacencia**: un directorio con una [[conceptos/listas-enlazadas|lista enlazada]] por vértice, conteniendo solo sus nodos adyacentes. Más eficiente en memoria para grafos dispersos (la mayoría de las aplicaciones reales).

## Recorrido (mención)
El libro anticipa, por analogía con los árboles, dos estrategias de recorrido: en **profundidad** (generaliza el pre-orden) y en **anchura** (generaliza el recorrido por niveles) — usando [[conceptos/pilas-y-colas|pila o cola]] respectivamente como estructura auxiliar, aunque el capítulo no desarrolla sus algoritmos en detalle.

## Equivalente en Python
No hay tipo grafo nativo. Se modela típicamente con un `dict` de listas de adyacencia (`{nodo: [vecinos]}`) o con la matriz como lista de listas. Bibliotecas como `networkx` proveen estructuras de grafo completas con algoritmos (camino más corto, conectividad, etc.) ya implementados.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/arboles]]
- [[conceptos/listas-enlazadas]]
- [[conceptos/pilas-y-colas]]
- [[conceptos/algoritmo-de-dijkstra]]
