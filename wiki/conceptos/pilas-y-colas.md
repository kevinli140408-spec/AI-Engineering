---
titulo: "Pilas y Colas (Stack, Queue, Bicola)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [pilas, colas, stack, queue, estructuras-dinamicas, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Pilas y Colas (Stack, Queue, Bicola)

Casos especiales de [[conceptos/listas-enlazadas|lista lineal]] que restringen **dónde** se puede insertar y eliminar — esa restricción es justamente lo que las hace útiles para ciertos patrones de procesamiento.

## Pila (stack) — LIFO
Inserción y eliminación ocurren **por un único extremo**, la **cima** (top). Por eso el último elemento insertado es el primero en salir: **LIFO** (*last-in, first-out*). Operaciones: `push`/`meter` (apilar) y `pop`/`sacar` (desapilar).

Se implementa con un array + un índice `cima` (incrementa/decrementa en cada `push`/`pop`), o con punteros (cada `push` reserva un nodo nuevo y lo enlaza como nueva cima).

**Aplicación clave**: las llamadas a subprogramas. Cuando A llama a B y B llama a C, las direcciones de retorno se apilan; C termina y retorna a B, B termina y retorna a A — el orden de retorno es exactamente el inverso al de las llamadas, el patrón LIFO. Esto es la base de la pila de llamadas que sustenta la [[conceptos/recursividad|recursividad]] (Cap. 14): cada llamada recursiva apila un nuevo "marco", y los casos base se resuelven desapilando en orden inverso.

## Cola (queue) — FIFO
Las eliminaciones ocurren por el **frente** y las inserciones por el **final**: **FIFO** (*first-in, first-out*) — el primero en entrar es el primero en salir. Modela colas de espera reales (impresoras, procesos en un sistema operativo, atención por orden de llegada).

Implementación con array: requiere dos índices `frente` y `final`. El problema práctico es que, sin reciclar espacio, `final` puede llegar al límite del array aunque queden huecos liberados a la izquierda. Soluciones: desplazar elementos (costoso), reestructurar al llenarse, o — la más eficiente — un **array circular**, donde la posición siguiente a la última se considera la primera (`final ← final mod max + 1`), sacrificando una posición del array para distinguir cola llena de cola vacía.

## Doble cola (bicola, deque)
Generaliza la cola permitiendo inserción **y** eliminación por **ambos extremos**. Variantes restringidas: entrada restringida (solo inserta al final) o salida restringida (solo elimina por el frente).

## Equivalente en Python
- Pila: una `list` nativa ya sirve — `append()`/`pop()` operan sobre el final en O(1).
- Cola / doble cola: `collections.deque` implementa exactamente esta estructura, con `append()`/`appendleft()`/`pop()`/`popleft()` en O(1) por ambos extremos — evita el costo O(n) de `list.pop(0)` para simular una cola con una lista común.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/listas-enlazadas]]
- [[conceptos/listas-python]]
- [[conceptos/recursividad]]
