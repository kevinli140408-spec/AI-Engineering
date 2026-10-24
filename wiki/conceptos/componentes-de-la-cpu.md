---
titulo: "Componentes Internos de la CPU"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-10-24
tags: [hardware, cpu, arquitectura-von-neumann]
fuentes: [arquitectura-computadoras-clase1-uade, arquitectura-computadoras-clase2-uade, arquitectura-computadoras-clase3-uade, arquitectura-computadoras-clase4-uade, arquitectura-computadoras-clase5-notas-uade]
---

# Componentes Internos de la CPU

Desarrollo detallado de la Unidad Central de Proceso (UCP/CPU) más allá de la división básica UC+UAL descrita en [[conceptos/organizacion-de-computadoras]], según el curso de Arquitectura de Computadoras de [[entidades/uade]].

## Unidad de Control (UC)

Coordina toda la ejecución: busca las instrucciones en memoria, las decodifica y dirige el tráfico de los [[conceptos/buses-de-sistema|buses]] y del resto de los componentes. Se la describe como "el cerebro dentro del cerebro".

## Unidad Aritmético-Lógica (ALU/UAL)

Ejecuta operaciones aritméticas (suma, resta; la multiplicación se implementa como sumas sucesivas y la división como restas sucesivas) y lógicas (AND, OR) sobre los operandos que recibe, usando un **acumulador** para resultados intermedios. En procesadores de 64 bits, opera con operandos de ese ancho.

## Registros

Memoria más pequeña y rápida que existe, integrada en la propia CPU. Tipos:
- **Propósito general**: datos y direcciones temporales.
- **Propósito específico**: contador de programa (dirección de la próxima instrucción) y registro de estado/flags (Z, N, C, V — detalle en [[conceptos/flags-del-procesador]]; usado también en el [[conceptos/interrupciones|ciclo de interrupción]]).

## Jerarquía de memoria por velocidad

`Registros > Caché (L1 > L2 > L3) > Memoria RAM > Almacenamiento secundario`. La **caché** es una memoria intermedia entre la CPU y la RAM, construida enteramente con transistores (a diferencia de la RAM, que combina transistores y capacitores), lo que la hace mucho más rápida pero más costosa; mitiga el [[conceptos/arquitectura-von-neumann|cuello de botella de Von Neumann]] trabajando con "paquetes" de datos anticipados.

Terminología de la caché ([[fuentes/arquitectura-computadoras-clase5-notas-uade]]): **cache hit** (el dato pedido ya está en caché) vs. **cache miss** (hay que ir a la RAM, con su latencia); **dirty bit**, marca de bloque modificado en caché que debe escribirse a RAM antes de ser reemplazado, garantizando coherencia. La caché también sirve como *scratch pad* de resultados intermedios.

## Reloj y PLL

La CPU se sincroniza con una señal de reloj externa (BCLK, típicamente ~100 MHz), que se multiplica mediante **PLLs** (Phase-Locked Loops) independientes por dominio: núcleos, memoria, fabric/interconexión interna, E/S. Intel usa una topología de anillo/malla (Ring/Mesh) y AMD una arquitectura de chiplets interconectados por **Infinity Fabric** — ver [[conceptos/ley-de-moore]]. A mayor frecuencia de reloj, mayor disipación de calor (ver [[conceptos/electricidad-basica]]).

## Núcleos y frecuencia de memoria

Un procesador puede tener múltiples **núcleos** (unidades de procesamiento independientes) y ejecutar múltiples **hilos** por núcleo. La memoria RAM tipo DDR transfiere datos en ambos flancos (subida y bajada) de cada ciclo de reloj, por lo que su tasa de transferencia (MT/s) es el doble de su frecuencia nominal (MHz).

## Referencias
- [[conceptos/organizacion-de-computadoras]]
- [[conceptos/tipos-de-procesadores]] — CPU frente a GPU, NPU, TPU y SoC
- [[conceptos/localidad-y-cache-de-procesadores]] — principios de localidad y filosofías de caché
- [[conceptos/arquitectura-von-neumann]]
- [[conceptos/buses-de-sistema]]
- [[conceptos/interrupciones]]
- [[conceptos/ley-de-moore]]
- [[conceptos/electricidad-basica]]
