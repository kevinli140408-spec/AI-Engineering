---
titulo: "Arquitectura de Computadoras — Clase 9: Almacenamiento, memoria y compatibilidad (apuntes UADE)"
tipo: fuente
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, almacenamiento, raid, pcie, tp, apunte]
---

# Clase 9: Almacenamiento, memoria y compatibilidad (apuntes UADE)

Apuntes reorganizados por tema (15 páginas) de la clase del **2026-10-13**, organizados el 2026-10-16, de [[entidades/uade]]. Continúan a [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]. Incluyen "Las 10 ideas que conviene llevarse", una autoevaluación de 12 preguntas y notas del organizador con datos a verificar.

## Dónde está desarrollado cada tema

| Tema | Página |
|---|---|
| TP (consigna, entregables, compatibilidad, rol del gerente), evaluación y oral, cronograma | [[analisis/tp-data-center-arquitectura-computadoras]] |
| Repaso de memoria: DRAM/SRAM, DDR, CAS, Dual Channel, RAM vs. VRAM/HBM, memoria virtual, jerarquía, RAM vs. NAND | [[conceptos/sram-y-dram]], [[conceptos/ddr-y-rendimiento-de-ram]], [[conceptos/dual-channel-y-fichas-de-memoria]], [[conceptos/gpu-y-vram]], [[conceptos/memoria-virtual]], [[conceptos/jerarquia-y-clasificacion-de-memorias]] |
| USB y Thunderbolt | [[conceptos/usb-y-thunderbolt]] |
| PCIe y arquitectura de E/S (Intel, AMD, Apple) | [[conceptos/pci-express]] |
| HDD, SSD, SATA/SAS/NVMe, M.2 | [[conceptos/discos-hdd-y-ssd]] |
| Medios ópticos y portátiles, cinta LTO, librerías robóticas | [[conceptos/cintas-lto-y-medios-de-archivo]] |
| RAID | [[conceptos/raid]] |
| NAS, SAN, switch y diagrama de red | [[conceptos/nas-san-y-redes-de-almacenamiento]] |

## Las 10 ideas centrales

El TP se evalúa por criterio técnico, no por costo · verificar compatibilidades (RAM máxima, versión y carriles PCIe, SO vs. aplicaciones) · DRAM densa y barata, SRAM rápida y cara · Dual Channel pide módulos idénticos · RAM busca baja latencia y VRAM alto ancho de banda · ancho de banda PCIe = velocidad por carril × carriles · NVMe sobre PCIe supera el límite de SATA · en RAID el SO ve un único disco · la cinta LTO es el medio ideal de archivo · NAS = Ethernet/TCP-IP, SAN = Fibre Channel con HBA.

## Aportes menores sobre memoria

- HBM (High Bandwidth Memory) tiene un ancho de banda muy superior al de la DDR convencional; en gaming a 4K, RAM + CPU procesan la lógica y VRAM + GPU la carga visual.
- Informática forense: se intenta recuperar datos de la RAM antes de que se pierdan tras el apagado; los data centers usan UPS/SAI.
- Ejemplo del apunte: "DDR5 a 3200 MHz llega a 6400 millones de transacciones por segundo" (unidad correcta: 6400 MT/s).

## Contradicciones y notas (resueltas el 2026-10-24 por delegación del usuario)

Criterios adoptados: **Dual Channel** → para el examen, módulos idénticos (postura de la cátedra), con la aclaración técnica en [[conceptos/dual-channel-y-fichas-de-memoria]]; **SRAM** → "varios transistores por celda (típicamente 6T)" en [[conceptos/sram-y-dram]]; **SSD** → no volátil, con riesgo de pérdida si pasa mucho tiempo sin energía; **Northbridge** → modelo clásico frente a procesadores modernos, ambos válidos según el contexto.

| Tema | Clase 9 | Otra fuente |
|---|---|---|
| Dual Channel | Módulos **idénticos** en velocidad y CAS | Clase 8 (nota): la mayoría de las plataformas aceptan latencias distintas y usan la del más lento; los kits idénticos siguen siendo lo recomendable |
| SRAM | 4-5 (o más) transistores por celda | Clase 8 (nota): 6T es lo habitual |
| SSD | La nota original los llamaba "volátiles" | El organizador corrige: no volátiles, aunque sin energía prolongada pueden perder datos |
| Northbridge | Los procesadores modernos ya no dependen de FSB ni Northbridge | [[fuentes/arquitectura-computadoras-clase4-apunte-uade]] lo presenta como parte de los buses: es el modelo clásico, no un error |

Datos que el propio organizador pide verificar: dos tablas PCIe con cifras distintas, capacidades de LTO-9 (12 o 18 TB) y LTO-10 (45 TB), mezcla de Gbps con GB/s, y SATA a 6 Gbps frente a "6 a 12 Gbps".

## Referencias
- Archivo original: `Clase_9_Apuntes_organizados.pdf` (movido a `raw/assets/Arquitectura de Computadoras/apuntes/`)
