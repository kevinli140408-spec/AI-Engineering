---
titulo: "Algoritmo de Dijkstra"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [grafos, algoritmos, camino-mas-corto]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Algoritmo de Dijkstra

Algoritmo clásico para encontrar el **camino más corto** entre un vértice origen y todos los demás vértices en un [[conceptos/grafos|grafo ponderado]] con pesos **no negativos**. El libro de Joyanes lo menciona solo de pasada, al introducir los grafos ponderados como estructura base para "problemas de camino más corto", sin desarrollar el algoritmo en detalle — esta página completa ese hueco con conocimiento general del área.

## Idea general (enfoque voraz/greedy)
1. Se asigna distancia 0 al vértice origen e infinito a todos los demás.
2. En cada paso, se selecciona el vértice no visitado con menor distancia acumulada conocida.
3. Se **relajan** sus aristas salientes: para cada vecino, si la distancia acumulada al origen más el peso de la arista es menor que la distancia actualmente registrada para ese vecino, se actualiza.
4. Se marca el vértice como visitado y se repite hasta procesar todos los vértices (o hasta alcanzar el destino buscado).

Es un algoritmo **voraz** (greedy): en cada paso toma la decisión localmente óptima (el vértice no visitado más cercano) confiando en que esto produce el óptimo global — válido precisamente porque no admite pesos negativos (un peso negativo podría hacer que una ruta "aparentemente peor" resultara mejor más adelante).

## Estructuras de datos involucradas
Una implementación eficiente típicamente usa una **cola de prioridad** (min-heap) para seleccionar rápidamente el vértice de menor distancia en cada iteración, y la [[conceptos/grafos|lista o matriz de adyacencia]] del grafo para recorrer los vecinos — conectando este algoritmo con las estructuras vistas en árboles y grafos del libro.

## Por qué su nombre aparece también fuera de grafos
El apellido de su creador, [[entidades/edsger-dijkstra|Edsger W. Dijkstra]], reaparece en el wiki en otro contexto: la crítica clásica a la sentencia `goto` (mencionada en [[conceptos/estructura-condicional]]) y la frase citada en [[conceptos/depuracion-y-pruebas]] sobre que "las pruebas muestran la presencia de errores, nunca pueden demostrar su ausencia" son también suyas — fue una figura central en la fundación de la programación estructurada y la [[conceptos/verificacion-formal|verificación formal]] de programas.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/grafos]]
- [[conceptos/estructura-condicional]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/verificacion-formal]]
- [[entidades/edsger-dijkstra]]
