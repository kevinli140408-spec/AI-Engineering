---
titulo: "Programación I — Clase 10: Recursividad"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, recursividad, torres-de-hanoi]
---

# Programación I — Clase 10: Recursividad

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Última clase del curso: [[conceptos/recursividad|recursividad]] — definiciones recursivas cotidianas, función factorial, "caso base"/"caso recursivo", el "teorema fundamental" (equivalencia recursión↔iteración), Fibonacci, recursividad sobre listas, y las [[conceptos/torres-de-hanoi|Torres de Hanoi]].

## Contenido principal
- Definición general de recursividad y ejemplos cotidianos (imágenes recursivas, definición recursiva de un identificador).
- Función factorial: derivación, código Python, prueba de escritorio para `n=4` y para `n=-1` (que nunca alcanza el caso base y produce `RecursionError`).
- Terminología explícita: caso base vs. caso recursivo.
- "Divide y vencerás" como técnica para identificar problemas aptos para solución recursiva.
- Potencia de un número natural como segundo ejemplo de recursión matemática simple.
- El "teorema fundamental": todo problema con solución iterativa admite solución recursiva y viceversa.
- Recursividad aplicada a listas: `imprimirlista()` y `buscarmayor()`, cada una en dos versiones (índice con valor por omisión vs. slicing).
- Serie de Fibonacci: fórmula, código, árbol de llamadas (ilustrando la explosión combinatoria/ineficiencia).
- Ventajas (elegancia, simplicidad) y desventajas (lentitud, consumo de memoria) de la recursividad.
- Torres de Hanoi: leyenda, reglas, estrategia de resolución, código `mover()`, fórmula de movimientos óptimos `2^n - 1` y su magnitud para 64 discos.
- Recomendaciones: nunca verificar el caso base con `while`/`for`; usar parámetros adicionales y el valor de retorno para comunicar información entre llamadas recursivas.

## Contraste con el resto de la wiki
[[conceptos/recursividad]] y [[conceptos/torres-de-hanoi]] (originadas en Joyanes Aguilar y Marzal et al.) ya cubrían en profundidad factorial, Fibonacci, Euclides, Hanoi, pila de llamadas y recursión directa/indirecta — prácticamente coincidiendo con esta fuente en sustancia. Lo nuevo que aporta: la terminología explícita "caso base"/"caso recursivo", el "teorema fundamental" nombrado como tal, el error `RecursionError` por ausencia de caso base alcanzable, los dos patrones de **recursividad sobre listas** (con índice y con slicing), y las recomendaciones prácticas de diseño (no mezclar `while`/`for` con la verificación del caso base).

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/recursividad]]
- [[conceptos/torres-de-hanoi]]
- [[conceptos/listas-python]]
