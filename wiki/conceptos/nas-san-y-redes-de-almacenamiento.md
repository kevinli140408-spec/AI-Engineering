---
titulo: "NAS, SAN y Redes de Almacenamiento"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [almacenamiento, nas, san, switch, redes, data-center, fibre-channel]
fuentes: [arquitectura-computadoras-clase9-apuntes-uade]
---

# NAS, SAN y Redes de Almacenamiento

## NAS vs. SAN

| | NAS (Network Attached Storage) | SAN (Storage Area Network) |
|---|---|---|
| Protocolo | TCP/IP | **Fibre Channel** (creado por IBM) |
| Medio | Red estándar: Ethernet, conector RJ45 | Fibra óptica de alta velocidad |
| Propósito | Almacenamiento compartido por red; ideal para entornos colaborativos | Acceso de alta velocidad para servidores |
| Velocidad | Menor que una SAN | Muy alta |
| Adaptador | Placa de red en ranura PCI/PCIe | **HBA** (Host Bus Adapter) en ranura PCI/PCIe |

Un NAS **no es solo un disco**: tiene procesador, RAM y sistema operativo propios, dedicados a gestionar almacenamiento e independientes de la arquitectura del servidor (p. ej. x86). Va desde pocos discos hasta 30, 60 o 90; hay versiones profesionales y compactas para editores o usuarios hogareños. Los volúmenes se arman con [[conceptos/raid]].

## Equipo profesional de ejemplo: QNAP TS-h1462XU-RP

Procesador Intel quad-core de arquitectura híbrida ([[entidades/intel]]), RAM DDR5, puertos duales de 2,5 Gbps, ranuras PCIe y M.2 2280 NVMe. Funciones: máquinas virtuales, alojar servicios (ej. WordPress), backup de Google Workspace y Microsoft 365, snapshots en la nube y gestión de volúmenes. Lo fundamental es el **ancho de banda** de lectura y escritura; la caché interna es memoria dedicada que acelera las grabaciones ([[conceptos/pci-express]], [[conceptos/discos-hdd-y-ssd]]).

## El switch y el diagrama de red

- El **switch** es el corazón del diagrama: conecta los equipos y todo el tráfico pasa por él, incluso el almacenamiento. Tiene un procesador interno que acelera el tráfico entre dispositivos.
- La LAN usa TCP/IP; el módem hogareño se conecta con cable de red RJ45. El mismo principio conecta discos y dispositivos al switch.
- Diagrama básico: estación de trabajo, PC/usuarios, servidor y almacenamiento (NAS/SAN), todos conectados al switch central. Es un entregable del TP ([[analisis/tp-data-center-arquitectura-computadoras]]).

## Temas de investigación sugeridos

SATA vs. SAS vs. NVMe; conectividad SAN vs. NAS (TCP/IP vs. Fibre Channel); función de los switches y de los HBA (tipos); productos de fabricantes (QNAP, Lenovo): modelos, comercialización y rol de las controladoras.

## Referencias
- [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[conceptos/cintas-lto-y-medios-de-archivo]]
