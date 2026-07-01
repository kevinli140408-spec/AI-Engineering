---
titulo: "Árboles (Generales, Binarios y de Búsqueda)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [arboles, arbol-binario, arbol-binario-de-busqueda, estructuras-no-lineales, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Árboles (Generales, Binarios y de Búsqueda)

A diferencia de las estructuras lineales ([[conceptos/listas-enlazadas|listas]], [[conceptos/pilas-y-colas|pilas/colas]]), donde cada elemento tiene un único "siguiente", un **árbol** permite bifurcaciones: cada nodo puede tener varios elementos siguientes. Es una estructura **no lineal**, definida recursivamente: un árbol es un nodo **raíz** más un conjunto de subárboles disjuntos.

## Terminología
**Hoja** (nodo terminal, sin hijos), **padre/hijo/hermano**, **nivel** (distancia desde la raíz), **altura** (nivel máximo + 1), **bosque** (colección de árboles). Todo nodo tiene un único padre, excepto la raíz.

## Árbol binario
Cada nodo tiene como máximo 2 hijos: **subárbol izquierdo** y **subárbol derecho**. Es la variante más fácil de implementar (no hace falta averiguar cuántas ramas salen de un nodo). Cualquier árbol general (o bosque) se puede convertir a un árbol binario equivalente mediante un algoritmo formal (enlazar cada nodo con su primer hijo por la izquierda, y con sus hermanos en cadena por la derecha).

**Representación**: con punteros (registro con campo dato + `subiz`/`subder`), con [[conceptos/listas-enlazadas|listas enlazadas]], o con [[conceptos/arrays-vectores-matrices|arrays]] (paralelos, o un único array donde el hijo izquierdo de `arbol[i]` está en `arbol[2*i]` y el derecho en `arbol[2*i+1]`).

## Recorridos
Tres formas recursivas de visitar todos los nodos, según cuándo se visita la raíz respecto a sus subárboles:
- **Pre-orden**: raíz → izquierdo → derecho.
- **In-orden**: izquierdo → raíz → derecho.
- **Post-orden**: izquierdo → derecho → raíz.

Los tres se definen de forma naturalmente recursiva — ver [[conceptos/recursividad]] y [[conceptos/pilas-y-colas]] (la pila de llamadas que sostiene cada recorrido).

## Árbol binario de búsqueda (ABB)
Generaliza la [[conceptos/algoritmos-busqueda|búsqueda binaria]] de un array a una estructura dinámica: en todo nodo, los valores del subárbol izquierdo son ≤ al nodo y los del derecho son mayores. Esto permite localizar, insertar y eliminar elementos sin el costo de desplazamiento que tienen los arrays ordenados. Propiedad clave: el **recorrido in-orden de un ABB produce los elementos en orden** — conecta directamente con [[conceptos/algoritmos-ordenamiento]].

La eliminación de un nodo tiene tres casos: hoja (se borra directo), un hijo (se sustituye por su hijo), dos hijos (se sustituye por su sucesor in-orden, el menor del subárbol derecho o el mayor del izquierdo).

## Equivalente en Python
Python no tiene un tipo árbol nativo; se modela con clases (`class Nodo: izq, der, valor`) o con un `dict` por nodo. El módulo `heapq` implementa un árbol binario especializado (montículo/heap) para encontrar mínimos eficientemente, y bibliotecas como `sortedcontainers` ofrecen estructuras tipo ABB balanceado para mantener colecciones ordenadas con inserción/búsqueda O(log n).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/listas-enlazadas]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/recursividad]]
- [[conceptos/grafos]]
