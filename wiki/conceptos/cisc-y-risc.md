---
titulo: "CISC y RISC (ISA)"
tipo: concepto
creado: 2026-09-15
actualizado: 2026-10-24
tags: [cpu, isa, cisc, risc, x86, arm]
fuentes: [arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase5-notas-uade]
---

# CISC y RISC

Dos filosofías de diseño del conjunto de instrucciones de un procesador.

## ISA: Instruction Set Architecture

Modelo abstracto que define **cómo el software controla la CPU**: la interfaz entre hardware y software. Comprende tipos de datos, registros y sus tamaños, buffers, manejo de errores y — su componente central — el **conjunto de instrucciones** (tres grandes categorías: operaciones con memoria, aritméticas y de control de la CPU). Las dos ISA dominantes hoy son **x86** (Intel/AMD) y **ARM** (Advanced RISC Machine).

## Comparación

| CISC (Complex Instruction Set) | RISC (Reduced Instruction Set) |
|---|---|
| Más instrucciones en la ISA | Menos instrucciones |
| Ciclos por instrucción **variables** | Ciclos por instrucción **fijos** |
| Tamaño de instrucción **variable** | Tamaño de instrucción **fijo** |
| Múltiples modos de direccionamiento a memoria | Solo direccionamiento simple |
| Opera valores en memoria y registros | Solo opera valores en registros |
| Código de alto nivel más simple; menos instrucciones por programa | Código más complejo; más instrucciones por programa |
| Más complejo → más costoso | Menos complejo → menor costo |

Historia: CISC nació en los años 50-60 para homogeneizar computadores; RISC surgió en los 70 buscando rendimiento con instrucciones simples (a costa de programas más largos). La regularidad RISC favorece el [[conceptos/pipelining-y-superescalaridad|pipelining]].

Según [[fuentes/arquitectura-computadoras-clase5-notas-uade]]:
- **Regla 80/20**: ~80% de las operaciones son simples (sumas, básicas); RISC (IBM y universidades, años 90; AS400, PowerPC) optimizó ese 80% y el 20% complejo se resuelve con instrucciones adicionales o software.
- En CISC la carga recae en el **hardware** (más consumo y calor); en RISC recae en el **compilador/software** (más instrucciones simples por programa). Ej.: `3+7` es una sola instrucción compleja en CISC vs. cargar-cargar-sumar-almacenar en RISC.
- **Coprocesadores**: en el 386 el punto flotante era un chip aparte; el 486 lo integró. Hoy x86 supera las 2.000 instrucciones.
- **Límite térmico (~2014)** → convergencia: núcleos heterogéneos (*efficiency* / *performance cores*, ej. Apple M1) en ambas filosofías.
- **Incompatibilidad de ISA**: un SO/binario x86 no corre nativo en [[entidades/arm|ARM]] y viceversa; los emuladores median con pérdida de rendimiento. La eficiencia RISC llevó ARM de los celulares (Android/iOS) a las notebooks (Apple Silicon).

## x86 vs x64

**x86** nombra la familia Intel 8086/80286/80386/80486 (la demanda de Intel por la marca numérica fracasó — los números no son registrables — y por eso la siguiente generación se llamó *Pentium*). Quedó como descriptor de procesadores de **32 bits**; **x64 (x86-64)** extiende la ISA a 64 bits, procesa 2⁶⁴ unidades por ciclo, maneja más RAM y es retrocompatible con código x86. Ver también [[conceptos/historia-de-la-computacion]].

## x86 vs ARM

| | x86 | ARM |
|---|---|---|
| Tipos de datos | 8/16/32/64 bits | 8/16/32/64 bits |
| Enteros con signo | [[conceptos/representacion-numeros-enteros|Ca2]] (16/32/64) | Ca2 (16/32/64) |
| Punto flotante | [[conceptos/punto-flotante-ieee754|IEEE 754]] | IEEE 754 (en algunos procesadores, por software para ahorrar energía) |
| Endianness | Little endian | Little **y** big endian, configurable independientemente del SO |

## Referencias
- [[fuentes/arquitectura-computadoras-clase5-uade]]
- [[conceptos/pipelining-y-superescalaridad]]
- [[conceptos/historia-de-la-computacion]]
- [[conceptos/endianness]] — Big vs. Little Endian con ejemplos (x86 vs. ARM)
