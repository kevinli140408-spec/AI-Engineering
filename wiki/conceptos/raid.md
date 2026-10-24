---
titulo: "RAID (Redundant Array of Independent Disks)"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [almacenamiento, raid, redundancia, disponibilidad, data-center]
fuentes: [arquitectura-computadoras-clase9-apuntes-uade]
---

# RAID

Unifica varios discos físicos en **una sola unidad lógica**, gestionada por una controladora (placa, componente integrado en el procesador, o una controladora PCIe adicional). Nació con discos mecánicos y hoy se usa también con SSD ([[conceptos/discos-hdd-y-ssd]]).

## Niveles

| Nivel | Cómo funciona | Redundancia / capacidad | Característica |
|---|---|---|---|
| **RAID 0** (striping) | Dos bloques llegan a la vez: uno a cada disco | Ninguna; capacidad = suma | Más ancho de banda; si falla un disco se pierde todo |
| **RAID 1** (mirroring) | Cada bloque se graba en ambos discos | Alta; capacidad = la de un disco | Sigue operando con un disco; *hot swap* |
| **RAID 5** | Striping + paridad distribuida (mín. 3 discos) | Tolera 1 falla; pierde 1 disco | Equilibrio velocidad/seguridad; reconstrucción |
| **RAID 6** | Como RAID 5 con doble paridad | Tolera 2 fallas; pierde 2 discos | Más seguridad, menos capacidad |
| **RAID 10** (1+0) | RAID 0 sobre pares espejo (RAID 1) | 50 % útil; tolera un disco por par | Alto rendimiento y máxima seguridad; preferido para bases de datos (hoy con SSD) |
| **RAID 50 / 60** | RAID 0 sobre ramas RAID 5 / 6 | Redundancia mucho mayor | Sistemas críticos de alta disponibilidad |
| **Triple paridad** | Tres bloques de paridad | Tolera hasta 3 discos | Máxima disponibilidad |

## Capacidad útil (ejemplos de la clase)

| Configuración | Cálculo | Útil |
|---|---|---|
| RAID 5 · 10 × 10 TB | 100 − 10 (1 de paridad) | **90 TB** |
| RAID 6 · 10 × 10 TB | 100 − 20 (2 de paridad) | **80 TB** |
| RAID 10 · 4 × 10 TB | 2 pares espejo × 10 TB | **20 TB** |
| RAID 10 · 4 SSD de 8 TB (32 TB) | La mitad queda para espejos | **16 TB** |

## Controladora y volúmenes

- Para el SO el conjunto es **un único disco físico sin formatear**; sobre él se crean particiones o volúmenes (D, E, F…) para distintas aplicaciones o servidores. Ej.: 4 × 10 TB en RAID 10 → 20 TB divisibles en varios volúmenes.
- Si un disco falla, la controladora activa alertas, pero el SO y las aplicaciones no se enteran y el trabajo continúa.
- **No se mezclan HDD y SSD** dentro de un mismo RAID (sí en arreglos separados, en bahías distintas).

## Disponibilidad y criticidad

Importa la **continuidad del servicio**, no solo el ancho de banda: tener backup no elimina el *downtime* (cambiar el disco y reinstalar puede llevar 4 a 6 horas). Sistemas críticos (sucursales bancarias, gobiernos, productoras 24 h) justifican alta redundancia (RAID 1, 10, 50, 60); pequeñas productoras o seguridad básica suelen usar NAS con RAID 1 o RAID 5 ([[conceptos/nas-san-y-redes-de-almacenamiento]]).

## Planificación con un calculador (ej. QNAP)

Variables: bahías (de 2 a 30 en equipos rackeables), tipo de disco (HDD de 2 a 24 TB; SSD de 30 o 61 TB) y nivel (0, 5, 6, 10, 50, 60). Ejemplo de 14 bahías: 6 × 16 TB + 4 × 10 TB + 4 × 4 TB. La salida muestra *Usable Space*, *Capacity required for data protection* y *Unused Space* (reservado para el SO del equipo). El calculador debe ajustarse a un equipo que soporte esa configuración.

**Para el oral**: no alcanza con "armamos RAID 6"; hay que explicar la capacidad útil y por qué ese nivel ([[analisis/tp-data-center-arquitectura-computadoras]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[conceptos/cintas-lto-y-medios-de-archivo]]
