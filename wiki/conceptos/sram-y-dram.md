---
titulo: "SRAM y DRAM: Construcción, Módulos y Sincronía"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, ram, sram, dram, dimm, sincronia]
fuentes: [arquitectura-computadoras-clase8-apunte-uade, arquitectura-computadoras-clase9-apuntes-uade]
---

# SRAM y DRAM

Las memorias centrales se clasifican según su construcción física ([[fuentes/arquitectura-computadoras-clase8-apunte-uade]]).

## SRAM vs. DRAM

| | SRAM (estática) | DRAM (dinámica) |
|---|---|---|
| Construcción | 100 % transistores en circuitos secuenciales (flip-flops, ver [[conceptos/alu-de-1-bit]]) | 1 transistor + 1 capacitor por bit |
| Guarda el bit | Por el estado de conmutación | Por la carga del capacitor |
| Velocidad | Mucho más rápida | Más lenta |
| Capacidad | Menor | Mayor (4, 8, 16, 32, 64 GB) |
| Costo / calor | Más cara y difícil de fabricar; se calienta | Más simple y barata |
| Refresco | No lo necesita | **Sí**, periódico |
| Uso | Caché y registros | Memoria principal (RAM) |

Para el examen: **SRAM = rápida, cara, poca capacidad; DRAM = más lenta, barata, mucha capacidad.** Una celda SRAM clásica usa **6 transistores** (la Clase 8 decía "3 a 4" y la Clase 9 "4-5 o más"; la nota de la Clase 8 corrige a 6T. **Criterio adoptado (2026-10-24)**: responder "varios transistores por celda (típicamente 6T)", que es compatible con las tres versiones; ver [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]). La DRAM es hasta ~10.000 veces más rápida que un SSD (NAND, no volátil). El consumo en reposo de la SRAM es bajo; la DRAM gasta energía en el refresco.

## El capacitor y el refresco

Con corriente continua el capacitor se carga hasta saturarse y luego se comporta como aislante; con alterna se carga y descarga constantemente. Como la información depende de una carga que se pierde con el tiempo, el sistema envía pulsos periódicos para refrescarla y mantener el nivel (por ejemplo, un "1"). Ver [[conceptos/electricidad-basica]].

## Módulos

| Módulo | Época | Descripción |
|---|---|---|
| Primeras RAM | Años 70 | 30 pines sobre la placa base |
| **SIMM** | Años 80-90 | Una línea de conectores; en ambas caras llevan la misma señal (redundantes); capacidad limitada |
| **DIMM** | Estándar actual | Contactos independientes en cada cara; canales de 64 bits |

## No sincrónicas vs. sincrónicas

- **No sincrónicas** (primeras DRAM): sin relación con el reloj; el procesador hacía una operación y luego enviaba la orden, generando esperas.
- **Sincrónicas** (actuales): se sincronizan con el reloj de la CPU mediante un divisor de frecuencia, en el flanco de subida.

Secuencia de una transferencia: (1) la CPU levanta la dirección en el bus de direcciones; (2) la orden (ej. *Read*) en el bus de control; (3) se mueven los datos por el bus de datos ([[conceptos/buses-de-sistema]]).

La evolución a doble tasa de datos está en [[conceptos/ddr-y-rendimiento-de-ram]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/jerarquia-y-clasificacion-de-memorias]]
