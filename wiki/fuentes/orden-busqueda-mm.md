---
titulo: "Métodos de Búsqueda y Ordenamiento"
tipo: fuente
creado: 2026-06-30
actualizado: 2026-06-30
tags: [algoritmia, busqueda, ordenamiento, uade]
---

# Métodos de Búsqueda y Ordenamiento

Fuente: presentación PPTX de la materia Fundamentos de Informática (Algoritmia), [[entidades/uade|UADE]]. Prof. Verónica Galati.

## Resumen
Desarrolla los [[conceptos/algoritmos-busqueda|algoritmos de búsqueda]] (secuencial, binaria) y los [[conceptos/algoritmos-ordenamiento|algoritmos de ordenamiento]] (selección, burbujeo, inserción) sobre [[conceptos/listas-python|listas]].

## Contenido principal
- **Búsqueda secuencial**: recorrido elemento por elemento; dos implementaciones (con bandera `encontrado` y con condición compuesta en el `while`); variante que cuenta ocurrencias.
- **Intercambio**: técnica base de los algoritmos de ordenamiento, usando variable auxiliar.
- **Método de Selección**: busca el menor de toda la lista y lo coloca en su posición, repitiendo con el resto.
- **Método de Burbujeo**: compara elementos consecutivos e intercambia si están desordenados; versión mejorada que detecta cuándo ya está ordenado.
- **Método de Inserción**: inserta cada elemento en su posición correcta desplazando (no intercambiando).
- **Búsqueda binaria**: requiere lista ordenada; divide el espacio de búsqueda a la mitad en cada paso (`centro = (izq+der)//2`).
- **Ordenamientos especiales**: ordenar según una clave derivada (ej. valor absoluto) mediante una función auxiliar.
- **Listas paralelas**: reordenar dos listas relacionadas (legajos y notas) manteniendo la correspondencia.
- Advertencia: ordenar es costoso; usar solo cuando sea necesario.

## Referencias

- [[conceptos/algoritmos-busqueda]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/listas-python]]
