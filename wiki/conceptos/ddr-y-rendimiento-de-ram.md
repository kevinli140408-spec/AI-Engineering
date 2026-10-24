---
titulo: "DDR y Rendimiento de la RAM"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, ram, ddr, ancho-de-banda, latencia-cas, prefetch]
fuentes: [arquitectura-computadoras-clase8-apunte-uade]
---

# DDR y Rendimiento de la RAM

## DDR (Double Data Rate)

Surge hacia el año 2000. **SDR** hace una transferencia por ciclo (flanco de subida); **DDR** transfiere en ambos flancos: dos por ciclo. La tasa efectiva es el doble de la frecuencia nominal: 1333 MHz × 2 = **2666 MT/s** (megatransferencias por segundo, unidad de las fichas actuales). Un reloj de 4400 MHz equivale a 8800 MT/s (el apunte decía "Mbps": error). **GDDR** es la variante para gráficos ([[conceptos/gpu-y-vram]]).

| Generación | MT/s | Ancho de banda aprox. | Voltaje | Prefetch |
|---|---|---|---|---|
| DDR1 | 200-400 | 3,2 GB/s | 2,5 V | 2n |
| DDR2 | 400-800 | 6,4 GB/s | 1,8 V | 4n |
| DDR3 | 800-1600 | 12,8 GB/s | 1,5 / 1,35 V | 8n |
| DDR4 | 1600-3200 | 25,6 GB/s | 1,2 V | 8n |
| DDR5 | 3200-8800 | ~51 GB/s (6400) | ~1,1 V | 16n |

Cada generación busca más velocidad y capacidad con menos voltaje; como `P = V × I`, menos voltaje es menos calor y permite más componentes por módulo. Los valores de DDR5 del apunte (~32 GB/s) corresponden a los más lentos; un DDR5-6400 mueve ~51 GB/s por canal de 64 bits. (El rango de MT/s de DDR1 y el tope de 8800 en DDR5 no figuran en la tabla del apunte: el primero es un dato agregado al wiki y el segundo viene de la corrección del propio apunte.)

## Ancho de banda y frecuencia

Analogía de la autopista: carriles (líneas del bus) × capacidad por carril. La velocidad depende del ancho y de la frecuencia: mucho ancho con frecuencia muy baja puede rendir menos que menos ancho con frecuencia alta.

**Ejemplos adicionales** (no figuran en el apunte): `GB/s = bits del bus × MT/s / 8`.
- DDR4-3200 (64 bits): 25,6 GB/s · DDR5-6400: 51,2 GB/s.
- GDDR7 de la RTX 5090 (512 bits, ~28 Gbps/pin): ~1,8 TB/s.

## Latencia CAS (CL)

Ciclos de reloj entre la orden de lectura y el primer dato; el "ping" de la memoria. Es una métrica de ciclos, no de tiempo. Regla: **alta frecuencia + baja latencia = rendimiento extremo**.

**Ejemplo adicional**: `ns = CL × 2000 / MT/s`. DDR4-3200 CL16 → 10 ns; DDR5-6400 CL32 → 10 ns. Un CL mayor no implica más lento si la frecuencia también es mayor.

## Prefetch

Oculta la latencia: anticipa lo que se necesitará y mueve paquetes de varias palabras de la RAM a la caché ([[conceptos/localidad-y-cache-de-procesadores]]). En DDR5 se mueven **16 bloques de 32 bits** por vez; como las instrucciones x86 tienen tamaño variable, se habla de bloques de datos fijos, no de instrucciones por ciclo.

## Overclocking

Forzar RAM, CPU o GPU ajustando voltaje, latencia y frecuencia. Sube mucho la temperatura; hay una línea fina entre el límite y el daño permanente. Los entusiastas usan refrigeración personalizada o nitrógeno líquido (el apunte decía hidrógeno). Intel, AMD y NVIDIA ofrecen perfiles seguros ([[conceptos/dual-channel-y-fichas-de-memoria]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/sram-y-dram]]
- [[conceptos/jerarquia-y-clasificacion-de-memorias]]
