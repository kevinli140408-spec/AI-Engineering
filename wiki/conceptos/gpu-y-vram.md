---
titulo: "GPU, VRAM y RAM: Ancho de Banda frente a Latencia"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [gpu, vram, gddr, blackwell, tops, ia, ancho-de-banda]
fuentes: [arquitectura-computadoras-clase8-apunte-uade, arquitectura-computadoras-clase9-apuntes-uade]
---

# GPU, VRAM y RAM

La memoria debe "acompañar" al procesador: la CPU (MIMD, pocos núcleos potentes) prioriza **baja latencia**; la GPU (SIMD, miles de núcleos simples) tolera algo de latencia pero necesita **alto ancho de banda** para alimentar miles de núcleos en paralelo ([[conceptos/tipos-de-procesadores]]). Regla práctica: CPU → RAM tipo DDR; GPU → VRAM tipo GDDR.

## RAM vs. VRAM

| | RAM (DDR) | VRAM (GDDR) |
|---|---|---|
| Prioridad | Baja latencia | Alto ancho de banda |
| Propósito | Sistema general y multitarea | Paralelismo masivo, render, IA |
| Ubicación | Placa madre (DIMM, reemplazable) | **Soldada** alrededor de la GPU |
| Bus de datos | 64 a 128 bits | Hasta 384 bits (RTX 3090) y 512 bits (RTX 5090) |
| Ancho de banda | ~32-51 GB/s por canal | 700 a 1.600+ GB/s; RTX 5090: más de 1,7 TB/s con 32 GB |

**HBM** (High Bandwidth Memory), citada en la Clase 9, tiene un ancho de banda muy superior al de la DDR convencional. La VRAM se considera externa al bus de sistema porque la GPU se conecta por PCIe ([[conceptos/pci-express]]). La diferencia fundamental es el ancho de banda. Como la VRAM va soldada, no se amplía. Ver [[conceptos/ddr-y-rendimiento-de-ram]]. Nota: el apunte da tres rangos de VRAM distintos, y dice que 512 bits dan "hasta 4 veces" el ancho de uno de 64 cuando son 8 veces solo en ancho de bus.

La GPU tiene su propia jerarquía de caché: L1 distribuida entre los núcleos y L2 que agrupa varios grupos. El "~328 KB" de L1 del apunte es dudoso (en la serie RTX 40 son 128 KB por multiprocesador).

## Anatomía de una GPU (RTX 5090)

| Componente | Función |
|---|---|
| CUDA Cores / shaders | Procesamiento gráfico general (hasta 21.760) |
| Tensor Cores | Operaciones de IA (cálculo tensorial) |
| RT Cores | Iluminación y trazado de rayos |
| VRAM (GDDR7) | Memoria rapidísima junto a la GPU |

Tareas gráficas (**TCL**): *Transform* (geometría a formato procesable), *Clipping* (descartar lo no visible), *Lighting* (interacción de la luz con las superficies).

## Arquitectura Blackwell ([[entidades/nvidia]])

Unifica gráficos e IA, porque ambos piden núcleos pequeños y mucho ancho de banda. Incluye renderizado neuronal, **DLSS 4** con Multi-Frame Generation (cuadros intermedios por IA), GDDR7, 4K a 240 Hz con ray tracing, y versiones desktop y notebook. La IA requiere cómputo matricial y tensorial, parecido al de una GPU: por eso GPU y TPU (de Google, hace ~10 años) se orientan a IA. Según el apunte, ~80 % de la producción de NVIDIA se destina a IA.

**TOPS** (Tera Operations Per Second, con enteros de 8 bits) mide la IA: una NPU de ~50 TOPS frente a la RTX 5090. El apunte da 1.352 AI-TOPS, pero NVIDIA publica ~3.300-3.400 (el 1.352 parece de la generación anterior; verificar la ficha).

## Hardware físico y métricas

- **Refrigeración**: doble ventilador, double flow through, cámara de vapor 3D.
- **PCIe**: hace falta una placa base con el slot adecuado (velocidad y distancia física) para que la GPU no quede limitada; la CPU debe poder alimentar ese ancho de banda.
- **FPS**: fluidez de la imagen; la generación de cuadros por IA pasa de 34 a 328 FPS en la comparativa, pero con fuerte componente de marketing: más FPS no es más calidad. **G-Sync** sincroniza monitor y GPU (evita el tearing).
- **Datos a verificar** de la RTX 5090: consumo (~575 W de placa, fuente de ~1000 W, no 850 W), relojes sobre 2 GHz (no 1770 MHz), 21.760 núcleos (no 21.600), Tensor Cores de 5.ª generación.

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/especificaciones-de-procesadores]]
