---
titulo: "Buses de Sistema"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-08-19
tags: [hardware, buses, arquitectura-von-neumann]
fuentes: [arquitectura-computadoras-clase2-uade, arquitectura-computadoras-clase3-uade]
---

# Buses de Sistema

Canales físicos que interconectan la CPU, la memoria y los dispositivos de E/S en la [[conceptos/arquitectura-von-neumann|arquitectura de Von Neumann]]. Su ancho (cantidad de líneas paralelas) determina prestaciones y capacidad de direccionamiento — ver [[conceptos/sistemas-de-numeracion]].

## Los tres buses internos

- **Bus de direcciones**: unidireccional (CPU → memoria); su ancho en bits determina la memoria máxima direccionable (`2ⁿ` direcciones posibles).
- **Bus de datos**: bidireccional; transporta el contenido efectivo; su ancho es un factor clave de las prestaciones del sistema.
- **Bus de control**: bidireccional; transporta señales de coordinación (lectura/escritura, habilitación, señal de reloj).

## Ciclo de lectura/escritura de memoria

**Lectura**: la Unidad de Control coloca una dirección en el bus de direcciones → envía señal de habilitación por el bus de control → la memoria responde colocando el dato en el bus de datos → el dato se guarda en un registro. **Escritura**: proceso inverso (la CPU coloca dato y dirección, y una señal de "escribir").

## Chipset

Conjunto de circuitos que gestiona la comunicación entre CPU, memoria y periféricos. Históricamente dividido en **Northbridge** (gestión de memoria/RAM y gráficos, cercano a la CPU por su velocidad) y **Southbridge** (periféricos más lentos: USB, discos, red). En procesadores modernos gran parte de esta función se integró directamente en el procesador (PCH — Platform Controller Hub, o I/O Die en diseños de chiplets).

## Buses internos vs. externos

El **bus de sistema** (datos + direcciones + control) es la "columna vertebral" que conecta CPU y RAM. Los **buses externos** conectan periféricos: PCIe (tarjetas gráficas y expansión), USB, SATA (almacenamiento) — con sus propios estándares de velocidad evolucionando de forma independiente (ej. PCIe 4.0 vs. 5.0).

## Referencias
- [[conceptos/arquitectura-von-neumann]]
- [[conceptos/componentes-de-la-cpu]]
- [[conceptos/organizacion-de-computadoras]]
- [[conceptos/sistemas-de-numeracion]]
