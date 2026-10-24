---
titulo: "Arquitectura de Computadoras — Clase 2: Semiconductores, Historia del Hardware y Von Neumann"
tipo: fuente
creado: 2026-08-19
actualizado: 2026-08-19
tags: [hardware, uade, clase2, arquitectura-von-neumann]
---

# Arquitectura de Computadoras — Clase 2

Segunda clase del curso de **Arquitectura de Computadoras** de [[entidades/uade]]. Fuente reconstruida a partir de 3 versiones: diapositivas del docente (`raw/assets/Arquitectura de Computadoras/2026-08-19-CLASE 2 - ARQ - VON NEUMANN.pdf`, 62 páginas, con datos numéricos y citas exclusivas), apuntes muy detallados tipo transcripción (`clase 2.pdf`, 96 páginas, la fuente más completa en desarrollo conceptual) y un resumen ejecutivo (`Arq de Comp_Clase 2.pdf`, 17 páginas).

## Contenido

- **Cierre del bloque de electricidad**: materiales conductores/aislantes/semiconductores, componentes pasivos (capacitor, inductor), diodo y transistor, rectificación — ver [[conceptos/semiconductores-y-transistores]]. El estado físico del transistor (circuito abierto/cerrado) se presenta como el origen físico del bit.
- **Ley de Moore** y evolución de la cantidad de transistores por generación de CPU (Intel 4004 a Apple M4 Ultra), incluyendo el debate actual sobre su vigencia (Jensen Huang/NVIDIA vs. Intel) — ver [[conceptos/ley-de-moore]].
- **Historia de la computación**: de ENIAC (1946) a la PC personal, la sociedad Intel-Microsoft, el origen de AMD y la nomenclatura x86, y la migración de Apple a ARM — ver [[conceptos/historia-de-la-computacion]].
- **Componentes internos de la CPU** en detalle: UC, ALU, registros, jerarquía de caché (L1/L2/L3), reloj/PLL — ver [[conceptos/componentes-de-la-cpu]].
- **Arquitectura de Von Neumann**, ampliando lo ya conocido con: ciclo de instrucción de 4 etapas (Fetch-Decode-Execute-**Write Back**, más granular que el ciclo de 3 pasos documentado previamente), sistema de buses (datos/direcciones/control) y su ciclo de lectura/escritura — ver [[conceptos/arquitectura-von-neumann]] (actualizada) y [[conceptos/buses-de-sistema]].
- **Interrupciones** (hardware, software, internas) y su ciclo completo (guardado de contexto en pila, vector de interrupciones) — tema nuevo respecto a lo ya documentado del curso de Fundamentos de Informática. Ver [[conceptos/interrupciones]].
- **Arquitectura Harvard** como contraste con Von Neumann — ver [[conceptos/arquitectura-harvard]].

## Diferencias entre las 3 fuentes

El deck de diapositivas (62p) aporta datos exclusivos: la cita de Jensen Huang, la tabla completa de transistores por CPU, y la mención de buses externos (PCIe/USB/SATA). Las notas de 96 páginas desarrollan cada concepto con mucho mayor detalle narrativo (incluye diagramas tipo Mermaid). El resumen de 17 páginas es el único con el detalle logístico de la actividad de reconocimiento de hardware y la consigna de tarea. No se detectaron contradicciones técnicas relevantes entre las tres fuentes.

## Páginas relacionadas
- [[conceptos/semiconductores-y-transistores]]
- [[conceptos/ley-de-moore]]
- [[conceptos/historia-de-la-computacion]]
- [[conceptos/componentes-de-la-cpu]]
- [[conceptos/arquitectura-von-neumann]]
- [[conceptos/buses-de-sistema]]
- [[conceptos/interrupciones]]
- [[conceptos/arquitectura-harvard]]
- [[entidades/gordon-moore]]
- [[entidades/uade]]
- [[analisis/estructura-curso-arquitectura-computadoras-uade]]
