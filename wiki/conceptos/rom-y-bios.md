---
titulo: "ROM y BIOS (ROM, PROM, EPROM, EEPROM)"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, rom, bios, eeprom, arranque]
fuentes: [arquitectura-computadoras-clase8-apunte-uade]
---

# ROM y BIOS

Al encender la computadora el sistema operativo todavía no tiene el control. El primer componente que actúa es una memoria con instrucciones grabadas que le indica al procesador qué hacer y dónde buscar las primeras instrucciones: el **BIOS**. Las instrucciones de arranque (y el testeo de hardware) son fijas; el BIOS se puede actualizar (*reflash*), pero la lógica fundamental permanece. Usa memorias **ROM** (Read Only Memory): de solo lectura y **no volátiles** ([[conceptos/jerarquia-y-clasificacion-de-memorias]]).

## La familia ROM

| Tipo | Cómo se programa | Cómo se borra | Notas |
|---|---|---|---|
| **ROM** | El cliente pide al fabricante que grabe las instrucciones; sale ya grabada (primeras ROM, años 60) | No se puede | Producción muy personalizada |
| **PROM** | El fabricante entrega el chip "vacío"; el cliente lo programa "quemando" la base de un transistor, que pasa a representar un 0 | No se puede | Un solo uso; el cambio es físico |
| **EPROM** | Se reprograma tras borrar | Luz ultravioleta por una ventana transparente, ~30 min; los transistores vuelven a "1" | Hay que sacar el chip; ciclos limitados |
| **EEPROM** | Se reprograma tras borrar | Eléctricamente, en el mismo circuito (ej. opera a 5 V y se borra con 20 V) | No hay que extraerla; ciclos limitados |

Evolución: ROM → PROM → EPROM → EEPROM; cada paso agrega flexibilidad, de grabada en fábrica a borrable eléctricamente.

## Notas

- Los semiconductores pueden cambiar de estado por luz, radiación o temperatura: por eso la luz UV "resetea" una EPROM ([[conceptos/semiconductores-y-transistores]]).
- Los ciclos de borrado admisibles son más que los "3 o 4" del ejemplo del apunte (decenas a miles según el chip); ese valor es solo ilustrativo.
- Los BIOS actuales (**UEFI**) se guardan en memoria **flash**, descendiente de la EEPROM.

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/organizacion-de-computadoras]] (la ROM como parte de la memoria principal)
