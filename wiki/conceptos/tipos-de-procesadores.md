---
titulo: "Tipos de Procesadores (CPU, GPU, NPU, TPU, DPU, SoC)"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [procesadores, gpu, npu, tpu, soc, flynn, simd, mimd]
fuentes: [arquitectura-computadoras-clase7-apunte-uade, arquitectura-computadoras-clase8-apunte-uade]
---

# Tipos de Procesadores

Más allá de la CPU clásica ([[conceptos/componentes-de-la-cpu]]), hay procesadores especializados según la carga de trabajo. Fuente: [[fuentes/arquitectura-computadoras-clase7-apunte-uade]].

## Arquitecturas dominantes

| | x86 (CISC) | ARM (RISC) |
|---|---|---|
| Uso tradicional | Servidores, estaciones de trabajo, gaming | Móviles, embebidos, Apple Silicon |
| Ejemplos | [[entidades/intel]], [[entidades/amd]] | Apple serie M, Qualcomm Snapdragon ([[entidades/arm]]) |

Las fronteras se corren: ARM ya compite en estaciones de trabajo (Apple) y PC (Qualcomm con Windows nativo, más rendimiento por vatio). Ver [[conceptos/cisc-y-risc]].

## Clasificación por tipo

| Procesador | Para qué sirve | Nota |
|---|---|---|
| **CPU** | Procesamiento general: unidad de control, ALU, registros y E/S | La unidad clásica |
| **GPU** | Renderizado gráfico y también IA | Misma arquitectura para ambos fines |
| **NPU** | IA directamente en hardware (modelos de lenguaje) | Integrada en chips de Intel, AMD y Apple |
| **TPU** | IA a gran escala (LLM) | Diseño de Google, para data centers |
| **DPU** | Flujos de datos a 10, 100 Gb/s o más | Libera a la CPU de gestionar esos flujos |
| **Cuántico** | Cómputo con qubits | Ver [[conceptos/computacion-cuantica]] |

NPU y TPU se distinguen por escala: la NPU va integrada en procesadores comerciales; la TPU, en grandes centros de datos. [[entidades/nvidia]] volcó gran parte de su negocio de GPU hacia IA, lo que aumentó la demanda de placas.

## System on Chip (SoC)

Un único chip con un sistema completo: CPU, GPU, NPU (hasta 30 o 40 TOPS), memoria unificada y, en AMD, hasta la interfaz de E/S. Ahorra espacio y mejora la eficiencia.

## Taxonomía de Flynn (1966)

Clasifica por la relación entre flujo de instrucciones y de datos:

| Sigla | Significado | Ejemplo |
|---|---|---|
| SISD | 1 instrucción, 1 dato | Procesador simple clásico |
| **SIMD** | 1 instrucción, N datos | **GPU** |
| MISD | N instrucciones, 1 dato | Poco común |
| **MIMD** | N instrucciones, N datos | **CPU moderna** (multicore) |

| | CPU (MIMD) | GPU (SIMD) |
|---|---|---|
| Núcleos | Pocos (6, 8, 24; servidores 80-90) | Miles (la RTX 5090 supera 21.700) |
| Núcleo | Potente y complejo | Pequeño y básico |
| Prioridad | Instrucciones variadas | Enorme ancho de banda de datos |

Ejemplo SIMD: subir el brillo de la pantalla es **una** instrucción aplicada a todos los píxeles a la vez.

Michael Flynn la publicó en **1966** (las notas de clase la ubicaban en los años 60 y los 70). La memoria que necesita cada una (latencia vs. ancho de banda) está en [[conceptos/gpu-y-vram]].

## Cómo leer publicidad de hardware

Preguntarse qué significa técnicamente cada término: la arquitectura (ej. Blackwell), la cifra de rendimiento (50 a 3300 TOPS), la refrigeración y los requisitos de energía.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
- [[conceptos/especificaciones-de-procesadores]]
- [[conceptos/localidad-y-cache-de-procesadores]]
