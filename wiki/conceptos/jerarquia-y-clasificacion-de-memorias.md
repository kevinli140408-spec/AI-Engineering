---
titulo: "Jerarquía y Clasificación de Memorias"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, jerarquia, volatilidad, latencia, acceso]
fuentes: [arquitectura-computadoras-clase8-apunte-uade]
---

# Jerarquía y Clasificación de Memorias

La jerarquía de memoria es un tema "inevitable" de examen, junto con volátil/no volátil, RAM vs. VRAM y memoria virtual ([[fuentes/arquitectura-computadoras-clase8-apunte-uade]]). Memoria es todo lo capaz de almacenar contenido.

## Interna vs. externa y volatilidad

| | Interna | Externa (almacenamiento) |
|---|---|---|
| Conexión | Directa al procesador y al bus de sistema ([[conceptos/buses-de-sistema]]) | Por interfaces: PCIe, SATA, USB, Thunderbolt |
| Ejemplos | RAM, BIOS (ROM), caché y registros | HDD, SSD, pendrives |

| Volatilidad | Ejemplos |
|---|---|
| **Volátil** (pierde datos sin corriente) | Registros, caché, RAM |
| **No volátil** | ROM/BIOS, HDD, SSD, pendrives |

**Error común**: creer que toda memoria interna es volátil. La volatilidad depende del tipo, no de la ubicación (la ROM es interna y no volátil). Flujo: CPU ↔ RAM (el "puente" volátil) ↔ almacenamiento.

## Métodos de acceso

| Método | Cómo funciona | Ejemplo |
|---|---|---|
| Aleatorio | Cualquier celda, de forma independiente; tiempo constante | RAM |
| Directo | Se localiza la zona por un índice y luego se accede | HDD (semialeatorio) |
| Secuencial | Hay que recorrer el soporte en orden | Cintas, casetes |
| Asociativo | Lógica de asociación dentro del chip; direccionamiento casi instantáneo | Caché |

Nota del apunte: la descripción de "asociativo" es una simplificación; en los textos de referencia (Stallings) el dato se localiza comparando parte de su contenido (tags), no su dirección. El apunte también llamaba "secuencial" y "directo" al HDD en distintos lugares: lo correcto es **directo**.

**Ciclo de lectura en RAM** (analogía del repartidor): bus de direcciones = la casa, bus de control = el pedido, bus de datos = el paquete.

## Métricas

| Métrica | Definición | Unidad |
|---|---|---|
| Tiempo de acceso (latencia) | Desde la orden hasta que el dato está en el bus de datos | ns (RAM), ms (discos) |
| Tiempo de ciclo | Tiempo de una operación completa | ns |
| Velocidad de transferencia | Rapidez con que se mueven datos | MB/s |

La latencia puede ser **temporal** (tiempo absoluto) o **CAS** (en ciclos de reloj; ver [[conceptos/ddr-y-rendimiento-de-ram]]). En RAM es constante; en HDD varía por el giro del plato y el cabezal. Un SSD no tiene partes móviles, así que su latencia es mucho menor (decenas de microsegundos).

## La pirámide

| Nivel | Velocidad | Capacidad | Costo por GB |
|---|---|---|---|
| 1. Registros (dentro del CPU) | La mayor | Muy pequeña | Muy alto |
| 2. Caché (dentro del CPU) | Muy rápida | MB | Alto |
| 3. RAM | Rápida | GB | Medio-alto |
| 4. SSD | Media | Cientos de GB a TB | Medio |
| 5. HDD | Lenta | TB | Bajo |
| 6. Cintas | La menor | Las mayores | El menor |

Al descender: **aumenta** la capacidad, **disminuye** la velocidad y **disminuye** el costo por GB. Los niveles 1 a 3 son internos; del 4 en adelante, almacenamiento externo. Ver [[conceptos/componentes-de-la-cpu]] y [[conceptos/localidad-y-cache-de-procesadores]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/organizacion-de-computadoras]]
- [[conceptos/rom-y-bios]] · [[conceptos/sram-y-dram]] · [[conceptos/memoria-virtual]]
- Almacenamiento externo (Clase 9): [[conceptos/discos-hdd-y-ssd]] · [[conceptos/cintas-lto-y-medios-de-archivo]] · [[conceptos/raid]] · [[conceptos/pci-express]] · [[conceptos/usb-y-thunderbolt]]
