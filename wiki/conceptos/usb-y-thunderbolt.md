---
titulo: "USB y Thunderbolt"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [conectividad, usb, thunderbolt, usb4, buses-externos]
fuentes: [arquitectura-computadoras-clase9-apuntes-uade]
---

# USB y Thunderbolt

Buses externos de conectividad ([[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]). Al evaluar un puerto hay que distinguir cuatro cosas: **potencia**, **velocidad de transferencia**, **protocolo de datos** y **tipo de conector**.

## USB

- "Puente de datos" serial entre periféricos y sistema (teclados, mouse, parlantes, celulares) que además entrega potencia eléctrica.
- Línea de tiempo: USB 1.0 (1996), USB 2.0 (2001), USB 3.0 (2007), USB4 / Thunderbolt (2022). USB4 llega a ~80 Gbps.
- Conectores: tendencia a **USB-A** (tradicional) y **USB-C** (estándar moderno). La Unión Europea obligó a estandarizar, lo que llevó a Apple a pasar de Lightning a USB-C.

## Thunderbolt

- Desarrollado por **Intel y Apple**. Alta velocidad, múltiples monitores 4K/8K (integra DisplayPort) y Power Delivery de hasta 100 W por el mismo cable.
- Es una **extensión externa del bus PCIe**: mete el protocolo PCIe dentro de Thunderbolt, así un disco externo opera a velocidades de bus interno, no de un USB 3.0 ([[conceptos/pci-express]]).
- Los cables deben ser los apropiados para el estándar: si no soportan la potencia o la velocidad, se limita el ancho de banda, fallan y pueden dañar componentes.

## USB4 vs. Thunderbolt

| | USB4 | Thunderbolt 4 / 5 |
|---|---|---|
| Velocidad | Base 40 Gbps (80 Gbps en v2.0) | TB4: 40 Gbps garantizados; TB5: hasta 80 Gbps (120 Gbps en modo boost para video) |
| Conector | USB-C | USB-C |
| Retrocompatibilidad | USB 2.0, USB 3.2, Thunderbolt 3 | USB 2.0, USB 3.2, USB4 |
| Ventaja | Estándar general de alta velocidad | Requisitos de seguridad y rendimiento más estrictos, certificación de [[entidades/intel]], mejor para video de calidad |

Los protocolos de USB4 y las últimas versiones de Thunderbolt convergen, lo que facilita la interoperabilidad entre ecosistemas (Apple y PC). Thunderbolt también figura entre las interfaces de almacenamiento externo de [[conceptos/jerarquia-y-clasificacion-de-memorias]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[conceptos/discos-hdd-y-ssd]]
