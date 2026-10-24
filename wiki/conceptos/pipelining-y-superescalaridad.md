---
titulo: "Pipelining y Superescalaridad"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-09-15
tags: [cpu, pipelining, paralelismo, arquitectura]
fuentes: [arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase5-notas-uade]
---

# Pipelining y Superescalaridad

Técnicas que evolucionan el [[conceptos/arquitectura-von-neumann|ciclo de instrucción]] secuencial para ejecutar más instrucciones por unidad de tiempo.

## Ciclo secuencial

En el esquema básico, cada instrucción atraviesa sus etapas (leer memoria de instrucciones → decodificar → buscar operandos → ejecutar) **una por vez**: la siguiente instrucción no empieza hasta que la anterior termina.

## Segmentación de cauce (pipelining)

Mejora **a nivel de organización**: el ciclo se divide en *n* etapas y se **superponen** — mientras una instrucción se ejecuta, la siguiente se decodifica y una tercera se capta.

- Explota el paralelismo entre instrucciones; objetivo: completar una etapa por ciclo de reloj.
- **Mejora la productividad (throughput) pero empeora la latencia** de cada instrucción individual, por la sincronización entre etapas.

### Conflictos (hazards)

| Conflicto | Causa | Mitigación citada |
|---|---|---|
| **Estructural** | Dos etapas usan el mismo recurso a la vez (ej. acceso simultáneo a memoria) | Menor tiempo de acceso a memoria |
| **Dependencia de datos** | El resultado de una instrucción es entrada de la siguiente | Buffer de ciclo |
| **Control** | Instrucciones de salto invalidan lo ya captado | — |

### Técnicas de mitigación modernas

Según [[fuentes/arquitectura-computadoras-clase5-notas-uade]]:
- **Prefetching**: anticipar y cargar en caché las próximas instrucciones.
- **Predicción de saltos (branch prediction) / especulación**: la CPU "adivina" el destino del salto y llena el pipeline; si erra, descarta lo procesado (penalización).
- **Ejecución fuera de orden (out-of-order)**: reordena dinámicamente instrucciones independientes para no frenar el cauce, preservando la consistencia lógica del resultado.
- Requisito de diseño: instrucciones de **tamaño uniforme** hacen predecibles los tiempos de cada etapa (ventaja RISC).
- Métrica de rendimiento: **FLOPS** (operaciones de punto flotante por segundo).

## Arquitecturas superescalares

**Múltiples cauces de instrucciones independientes**, cada uno a su vez segmentado y con su propio set de unidades funcionales (ej. varias ALU). Pueden iniciarse varias instrucciones en el mismo ciclo (*multiple issue processors*), superando la productividad de una instrucción por ciclo.

## Multithread y multicore

- **Thread**: hilo de ejecución de un proceso, manejado por el sistema operativo; el código del programa debe soportar y especificar el uso de multithread.
- **Multicore**: núcleos físicos independientes (ver [[conceptos/componentes-de-la-cpu]]).

## Relación con CISC/RISC

La regularidad de las instrucciones RISC (tamaño y ciclos fijos) facilita el pipelining — una de las motivaciones de esa filosofía de diseño: ver [[conceptos/cisc-y-risc]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase5-uade]]
- [[conceptos/arquitectura-von-neumann]]
- [[conceptos/componentes-de-la-cpu]]
