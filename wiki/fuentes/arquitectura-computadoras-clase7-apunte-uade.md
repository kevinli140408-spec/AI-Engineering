---
titulo: "Arquitectura de Computadoras — Clase 7: Procesadores modernos (apunte UADE)"
tipo: fuente
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, procesadores, cache, fabricacion, especificaciones, tp, apunte]
---

# Clase 7: Procesadores modernos (apunte UADE)

Apunte organizado (13 páginas) de la Clase 7 de [[entidades/uade]]. Abre la **segunda etapa** del curso: tipos de procesadores, memorias, almacenamiento e integración en sistemas reales. Continúa a [[fuentes/arquitectura-computadoras-clase6-apunte-uade]]. El apunte salió de la transcripción de la clase, por eso marca muchas cifras como dudosas.

## Contenido y dónde está desarrollado

| Tema | Página |
|---|---|
| CPU, GPU, NPU, TPU, DPU, SoC; Flynn (MIMD vs. SIMD) | [[conceptos/tipos-de-procesadores]] |
| Del GHz al multinúcleo; localidad temporal/espacial; Intel vs. AMD 3D V-Cache | [[conceptos/localidad-y-cache-de-procesadores]] |
| Computación cuántica | [[conceptos/computacion-cuantica]] |
| Silicio → oblea → fotolitografía → encapsulado | [[conceptos/fabricacion-de-microprocesadores]] |
| Costos, ASML, Taiwán, política industrial | [[conceptos/geopolitica-de-semiconductores]] |
| Fichas técnicas, binning, turbo, núcleos híbridos, potencia | [[conceptos/especificaciones-de-procesadores]] |

Entidades: [[entidades/intel]], [[entidades/amd]], [[entidades/nvidia]], [[entidades/tsmc]], [[entidades/arm]].

## Revisión del primer parcial

- Errores sobre todo **conceptuales**: los temas teóricos pedían una definición clara, no un desarrollo extenso. Dificultades: el **ciclo de instrucción** (qué hace cada paso, definible en una línea) y las **interrupciones** (llamado externo al procesador y sus tipos). Ver [[conceptos/arquitectura-von-neumann]] e [[conceptos/interrupciones]].
- Consejo: **seguir la consigna** y no responder lo que no se pidió.
- Procedimiento: revisión ordenada en el escritorio; los reclamos requieren evidencia de error de corrección.

## Segunda etapa y TP de data center

- Ejes: procesadores (CPU, GPU, TPU, NPU, DPU, cuánticos), memorias, almacenamiento (SSD) e integración en PC, estaciones de trabajo, servidores, mainframes y cuánticas.
- **TP**: simula un rol profesional en un data center. Pasos: (1) analizar los requerimientos de la aplicación (base de datos, videojuego); (2) elegir el tipo de sistema; (3) definir procesador, memoria y almacenamiento. La **compatibilidad de componentes** es criterio central (ej. DDR5 con el procesador elegido).
- Modalidad: TP grupal + informe escrito individual **obligatorio** (si no se aprueba, no se rinde el segundo parcial) + defensa oral individual.
- Fechas del apunte: **2026-11-10** entrega del TP grupal y **2026-11-17** segundo parcial (defensa individual). El apunte da día y mes sin año; se asumió el año de cursada, **a confirmar con el docente**.

## Actividades propuestas

Comparar un procesador Intel y uno AMD (frecuencia base y máxima, núcleos, caché, gestión térmica, chiplets); repetirlo con Apple M5 y Qualcomm Snapdragon; anotar términos desconocidos. Cada campo de la ficha sirve para justificar el hardware del TP.

## Erratas y datos a verificar (según el propio apunte)

- "Ciclo de construcción" = ciclo de instrucción; "unidad de control de salida" = unidad de entrada/salida; "bases como SEM" y "Intel CityBoost" son términos ininteligibles o inexistentes.
- Las cifras de cuántica, fabricación, TSMC, Apple y Core Ultra están marcadas en cada página temática; para el TP conviene contrastarlas con fuentes oficiales.

## Referencias
- Archivo original: `Clase_7_Apunte.pdf` (movido a `raw/assets/Arquitectura de Computadoras/apuntes/`)
