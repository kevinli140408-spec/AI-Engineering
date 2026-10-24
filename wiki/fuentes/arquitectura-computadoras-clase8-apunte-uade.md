---
titulo: "Arquitectura de Computadoras — Clase 8: Memorias internas (apunte UADE)"
tipo: fuente
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, memoria, ram, vram, gpu, tp, apunte]
---

# Clase 8: Memorias internas (apunte UADE)

Apunte organizado (19 páginas, salido de una transcripción automática) de la Clase 8 de [[entidades/uade]]. Continúa a [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]. Hoy: memorias internas y comparación RAM vs. VRAM; la próxima clase, memorias externas (HDD, SSD, NVMe, PCIe, M.2, Thunderbolt) y luego tipos de computadoras.

## Dónde está desarrollado cada tema

| Tema | Página |
|---|---|
| CPU vs. GPU, Blackwell, TOPS, RAM vs. VRAM | [[conceptos/gpu-y-vram]] (y [[conceptos/tipos-de-procesadores]]) |
| Interna/externa, volátil, métodos de acceso, métricas, pirámide | [[conceptos/jerarquia-y-clasificacion-de-memorias]] |
| BIOS y familia ROM | [[conceptos/rom-y-bios]] |
| SRAM vs. DRAM, SIMM/DIMM, sincronía | [[conceptos/sram-y-dram]] |
| DDR, MT/s, ancho de banda, CAS, prefetch, overclocking | [[conceptos/ddr-y-rendimiento-de-ram]] |
| Dual Channel, kits, XMP/EXPO, ECC, números de parte, instalación | [[conceptos/dual-channel-y-fichas-de-memoria]] |
| Big/Little Endian | [[conceptos/endianness]] |
| Paginación y memoria en celulares | [[conceptos/memoria-virtual]] |

## Repaso y hábitos de estudio

- Repaso de la Clase 7: hojas de especificaciones Intel/AMD, tablas comparativas y x86 vs. ARM (Apple M5 y Samsung) — [[conceptos/especificaciones-de-procesadores]].
- **Glosario personal**: anotar cada término desconocido con una definición propia (Tensor, RT, DLSS, ray tracing, renderizado neuronal). Tema a investigar: "humanos digitales".
- Se recomienda el glosario técnico y las guías de números de parte de Kingston.

## TP N° 2: gestión de un data center

- **Rol**: gerente de un data center; diseñar la configuración para ejecutar aplicaciones dadas.
- **Entregables**: análisis de requerimientos (specs de las aplicaciones o similares); componentes con **compatibilidad garantizada**; listado de compra con justificación técnica de cada ítem; **diagrama de red** con la interconexión de los equipos; entrega y defensa.
- Aplicación directa: RAM con la capacidad, MT/s y latencia que el procesador soporte; kits en Dual/Quad Channel; ECC y memorias certificadas en servidores; verificar siempre el número de parte. Ver la logística en [[fuentes/arquitectura-computadoras-clase7-apunte-uade]].

## Erratas y tensiones con otras fuentes

| Tema | Apunte original | Corrección |
|---|---|---|
| Taxonomía de Flynn | "década del 70" (Clase 7: "años 60") | Publicada en **1966**; se actualizó [[conceptos/tipos-de-procesadores]] |
| TOPS de la RTX 5090 | 3.300 (Clase 7) vs. 1.352 (Clase 8) | NVIDIA publica ~3.300-3.400; el 1.352 parece de la generación anterior |
| RTX 5090 | 850 W, 1770 MHz, 21.600 núcleos | ~575 W de placa, >2 GHz, 21.760 CUDA cores |
| SRAM | 3 a 4 transistores por bit | 6T es lo habitual |
| DDR5 | "~32 GB/s" y "2666 millones de transacciones" | Hasta 8800 MT/s; 6400 MT/s ≈ 51 GB/s; la unidad es MT/s, no Mbps |
| "SIM", "UBIM", "QCUBIM", "iTracing" | — | SIMM, UDIMM/CUDIMM, ray tracing |
| HDD | "secuencial" y "directo" | **Directo** (semialeatorio); secuencial son las cintas |
| Memoria virtual | Años 80 | Años 60 (Atlas); popular en PC en los 80 |
| Overclocking extremo | Hidrógeno líquido | Nitrógeno líquido |
| ECC | Reintento y marca de bloque "malo" | Bits extra de verificación, corrección de 1 bit (tipo Hamming) |

Sin contradicciones con páginas previas del wiki, salvo el ajuste de Flynn ya aplicado. Los ejemplos de cálculo de ancho de banda, CL→ns y endianness de 4 bytes **no figuran en la clase**: los agregó quien organizó el apunte y están marcados como "adicionales" en cada página.

## Referencias
- Archivo original: `Clase_8_Apunte.pdf` (movido a `raw/assets/Arquitectura de Computadoras/apuntes/`)
