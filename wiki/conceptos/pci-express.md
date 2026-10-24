---
titulo: "PCI Express (PCIe) y Arquitectura de E/S Moderna"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [pcie, carriles, ancho-de-banda, entrada-salida, compatibilidad]
fuentes: [arquitectura-computadoras-clase9-apuntes-uade]
---

# PCI Express (PCIe) y Arquitectura de E/S Moderna

El rendimiento de cualquier dispositivo PCIe (SSD, placa de red, GPU, adaptadores) depende de dos parámetros:

- **Generación**: velocidad de cada carril individual. Mayor número = más moderna y rápida.
- **Carriles (lanes)**: se indican como x4, x16… y determinan cuántas vías paralelas hay.

Analogía de la autopista: la generación es el límite de velocidad y los carriles son las pistas. Una versión lenta con muchos carriles puede mover más datos que una rápida con pocos. **Ancho de banda = velocidad por carril × cantidad de carriles.**

## Valores de referencia

| Versión | GT/s por carril | Por carril | x4 | x16 |
|---|---|---|---|---|
| 1.0 | 2,5 | 250 MB/s | 1 GB/s | 4 GB/s |
| 2.0 | 5 | 500 MB/s | 2 GB/s | 8 GB/s |
| 3.0 | 8 | ~1 GB/s | ~4 GB/s | ~15,8 GB/s |
| 4.0 | 16 | ~2 GB/s | ~8 GB/s | ~31,5 GB/s |

Ejemplos de la clase: Gen 2.0 x4 = 500 MB/s × 4 = 2.000 MB/s; Gen 3.0 x4 = ~1.000 MB/s × 4 = 4.000 MB/s. Al duplicar la versión con los mismos carriles se duplica el ancho de banda. Los valores de la tabla son aproximados: el apunte tenía dos tablas con cifras distintas y el organizador usó la velocidad de referencia de la clase; verificar en la especificación oficial.

## Techo de rendimiento

La capacidad del procesador para gestionar versión y carriles define el techo del sistema. Si un componente pide PCIe 5.0 y la CPU soporta una versión anterior, queda limitado. Si faltan carriles para SSD + placa de video + placa de sonido a la vez, el hardware funciona, pero a velocidad reducida. Esto entra en la planilla de compatibilidades del TP ([[analisis/tp-data-center-arquitectura-computadoras]]).

## Arquitectura de E/S moderna

| Plataforma | Cómo se conecta la E/S |
|---|---|
| [[entidades/intel]] | Directo a la CPU: GPU (PCIe), NVMe (PCIe), Thunderbolt. Vía **PCH** (Platform Controller Hub): SATA y USB |
| [[entidades/amd]] Ryzen | **Infinity Fabric** comunica los componentes internos; controladores de RAM, PCIe y GPU integrados en el procesador |
| Apple Silicon | SoC con CPU, GPU, Neural Engine, controlador de memoria y de E/S (PCIe, Thunderbolt) en un chip; **no ampliable** (RAM en capacidades fijas: 12, 24, 48 GB…), por eso hay que elegir el equipo exacto |

Los procesadores modernos ya no dependen de un FSB compartido ni de un Northbridge: gestionan memoria, carriles PCIe y buses directamente. Es un matiz respecto del modelo clásico de [[fuentes/arquitectura-computadoras-clase4-apunte-uade]] (Northbridge/Southbridge), que sigue siendo válido como esquema conceptual. Ver [[conceptos/buses-de-sistema]].

La VRAM se considera externa al bus de sistema porque la GPU se conecta por PCIe ([[conceptos/gpu-y-vram]]). NVMe corre sobre PCIe ([[conceptos/discos-hdd-y-ssd]]); Thunderbolt es su extensión externa ([[conceptos/usb-y-thunderbolt]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[conceptos/especificaciones-de-procesadores]]
