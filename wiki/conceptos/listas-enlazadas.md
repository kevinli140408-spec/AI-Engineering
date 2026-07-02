---
titulo: "Listas Enlazadas (Punteros y Estructuras Dinámicas)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [listas-enlazadas, punteros, estructuras-dinamicas, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Listas Enlazadas (Punteros y Estructuras Dinámicas)

A diferencia de los [[conceptos/arrays-vectores-matrices|arrays]] (estructuras **estáticas**, tamaño fijo en memoria), las **estructuras dinámicas de datos** crecen y se contraen durante la ejecución del programa. Están formadas por **nodos** — variables dinámicas con al menos un campo de dato y un campo **enlace** (puntero) que referencia al siguiente nodo.

## Puntero
Un **puntero** (apuntador) es una variable cuyo valor es la dirección de otra variable. Operaciones básicas: inicialización (`p ← nulo`), asignación (`p ← q`), comparación, `reservar(p)` (pedir memoria) y `liberar(p)` (devolverla). [[entidades/lenguaje-c|C/C++]]/Pascal/Ada usan punteros explícitos; Java/C# no exponen punteros pero almacenan referencias a objetos con recolección automática de basura; FORTRAN/COBOL (sin tipo puntero) simulan el enlace con un índice entero sobre un array.

## Lista simplemente enlazada
Cada nodo apunta solo al siguiente; el último apunta a `nulo`. Operaciones centrales:
- **Inserción**: `reservar` un nodo nuevo, asignar el dato, y enlazarlo entre `anterior` y `anterior→.sig` (o al inicio si `anterior = nulo`).
- **Eliminación**: redirigir `anterior→.sig` para saltar el nodo a borrar, luego `liberar` su memoria.
- **Recorrido/búsqueda**: solo secuencial, desde el primer nodo — no hay acceso aleatorio como en un array.

Sin soporte nativo de punteros, se puede implementar igual con dos arrays paralelos: uno de datos y otro de enlaces (índices), manteniendo además una "lista de vacíos" (espacios libres encadenados) para reservar/liberar posiciones.

## Lista circular
El último nodo, en vez de apuntar a `nulo`, apunta de nuevo al primero. Permite recorrer la lista completa desde cualquier nodo y hace más eficientes la concatenación/división de listas, a costa de riesgo de bucles infinitos (se mitiga con un nodo **cabecera** especial).

## Lista doblemente enlazada
Cada nodo tiene dos punteros: `ANT` (anterior) y `SIG` (siguiente), permitiendo recorrer la lista en ambos sentidos. Ocupa más memoria por nodo que una lista simple, a cambio de esa flexibilidad.

## Equivalente en Python
Python no expone punteros ni nodos manuales: la `list` es un array dinámico (no una lista enlazada) que ya resuelve inserción/recorrido con métodos nativos (`insert()`, `append()`, `pop()` — ver [[conceptos/listas-python]]). El módulo `collections.deque` está implementado internamente como una lista doblemente enlazada de bloques, optimizada para inserciones/eliminaciones en ambos extremos en O(1) — el análogo práctico más cercano a lo descrito en este capítulo.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/listas-python]]
- [[conceptos/pilas-y-colas]]
- [[conceptos/estructuras-registros]]
- [[entidades/lenguaje-c]]
