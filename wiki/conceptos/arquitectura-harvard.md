---
titulo: "Arquitectura Harvard"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-08-19
tags: [hardware, arquitectura-von-neumann, sistemas-embebidos]
fuentes: [arquitectura-computadoras-clase2-uade, arquitectura-computadoras-clase3-uade]
---

# Arquitectura Harvard

Diseño de computadora alternativo a la [[conceptos/arquitectura-von-neumann|arquitectura de Von Neumann]], con **memorias y buses separados** para instrucciones y datos.

## Comparación con Von Neumann

| Aspecto | Von Neumann | Harvard |
|---|---|---|
| Memoria | Única, compartida | Separada (instrucciones / datos) |
| Buses | Uno compartido | Dos independientes |
| Ejecución | Secuencial (no puede leer instrucción y dato a la vez) | Paralela (lee instrucción y dato simultáneamente) |
| Flexibilidad de tamaño instrucción/dato | Alta (mismo espacio) | Menor (tamaños fijos por diseño) |
| Costo histórico | Menor | Hasta 10x mayor |

La separación de memorias en Harvard elimina el [[conceptos/arquitectura-von-neumann|cuello de botella de Von Neumann]] al permitir el acceso simultáneo a instrucción y dato, a cambio de mayor complejidad y costo de fabricación.

## Uso actual

Las computadoras de propósito general (PCs, notebooks, servidores, smartphones) siguen basándose en Von Neumann por su flexibilidad y menor costo. La arquitectura Harvard (o variantes híbridas) se reserva para **sistemas embebidos especializados** que priorizan velocidad y previsibilidad sobre flexibilidad — el curso menciona como ejemplo el procesador de un tomógrafo médico.

## Referencias
- [[conceptos/arquitectura-von-neumann]]
- [[conceptos/buses-de-sistema]]
- [[conceptos/componentes-de-la-cpu]]
