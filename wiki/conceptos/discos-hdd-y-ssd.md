---
titulo: "Discos HDD y SSD (SATA, SAS, NVMe, M.2)"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [almacenamiento, hdd, ssd, nvme, m2, sata, bloques, fragmentacion]
fuentes: [arquitectura-computadoras-clase9-apuntes-uade]
---

# Discos HDD y SSD

El almacenamiento es **no volátil**: conserva la información sin energía ([[conceptos/jerarquia-y-clasificacion-de-memorias]]).

## HDD (disco magnético)

- Los datos se graban como bloques magnéticos mínimos (0 y 1). Un cabezal se posiciona sobre platos que giran a velocidad constante (ej. 7.200 RPM) y se desplaza radialmente. Cada plato tiene dos caras: **cabezales = 2 × platos** (4 platos → 8 cabezales).
- El cabezal "vuela" sin tocar el plato: un golpe, vibración o polvo causa un **head crash** (raya el plato, se pierden datos). Los imanes potentes pueden borrar la información. Los discos actuales (hasta ~60 TB) vienen sellados y rellenos de un gas más denso que el aire (ej. argón).
- Factores de forma: 2,5" (laptops) y 3,5" (servidores y desktop).

**Fragmentación**: tras grabar y borrar muchas veces, los archivos quedan en bloques dispersos. Archivo contiguo ~2 ms; fragmentado hasta ~25 ms; la desfragmentación los junta.

**Tamaño de bloque** (se define al formatear):

| 4K (pequeño) | 64K (grande) |
|---|---|
| Ideal para archivos chicos; no desperdicia espacio. Con archivos grandes puede aumentar la fragmentación | Ideal para fotos y videos (lectura más rápida con datos contiguos). Con archivos chicos genera **slack space**: el bloque queda ocupado y el resto inutilizable |

**¿Por qué un disco "trae menos" de lo que dice la caja?** El fabricante usa base 10 (1 KB = 1.000) y el SO base 2 (1.024); la capacidad física es la misma ([[conceptos/sistemas-de-numeracion]]).

## SSD

- 100 % electrónico, sin partes móviles; tecnología **Flash (NAND)** que persiste datos sin energía. Capacidades de hasta 16 TB (30 y 61 TB en modelos empresariales). Más de 10 veces más rápido que un HDD; los HDD dan más capacidad por menos dinero (12, 14 TB o más).
- Los primeros SSD imitaron la estructura de los discos mecánicos (índice, acceso directo hacia afuera); internamente son de acceso aleatorio, como la RAM.
- **Volatilidad**: la nota original los llamaba "volátiles" sin energía; en rigor son no volátiles, pero **sin alimentación prolongada pueden perder datos** (meses o pocos años). La DRAM es hasta ~10.000 veces más rápida que un SSD y sí es volátil ([[conceptos/sram-y-dram]]).

## Interfaces

| Interfaz | Uso | Velocidad |
|---|---|---|
| **SATA** | HDD y primeros SSD | 6 Gbps (la nota llega a decir ~12 Gbps) |
| **SAS** | HDD en servidores; más seguridad y velocidad | 12 Gbps (hasta 24) |
| **NVMe** | SSD de alto rendimiento; corre sobre [[conceptos/pci-express]] | 10× a 20× SATA; latencias de microsegundos |

NVMe deja atrás el cuello de botella de SATA, pero es menos rápido que la DRAM. Unidades: la nota mezcla Gbps y GB/s (NVMe "~7 GB/s" según el contexto); verificar.

## Formato M.2

SSD pequeño y alargado que se pincha directo en la placa, pegado al bus PCIe; sirve para SO o caché y libera bahías. Nomenclatura: ancho y largo en mm (**M.2 2280 = 22 × 80 mm**; anchos 12, 16, 22, 30; largos 42 a 110 mm). A mayor largo, más chips NAND (de 1-3 a 8) y más capacidad. El slot acepta dos tipos de disco, pero cada uno es solo uno: **M.2 SATA** (~600 MB/s) o **M.2 PCIe/NVMe** (controlador propio, muy superior).

## Referencias
- [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[conceptos/raid]]
- [[conceptos/cintas-lto-y-medios-de-archivo]]
