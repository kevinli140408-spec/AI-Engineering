---
titulo: "Arquitectura de Computadoras — Clase 5: Notas de clase (UADE)"
tipo: fuente
creado: 2026-09-15
actualizado: 2026-09-15
tags: [arquitectura-de-computadoras, uade, cisc, risc, cache, notas-de-clase]
---

# Clase 5: Notas de clase (UADE)

Notas HoverNotes de la grabación de la clase del **2026-09-01** del curso de Arquitectura de Computadoras de [[entidades/uade]]. Complementan las diapositivas de [[fuentes/arquitectura-computadoras-clase5-uade]]. Existían tres copias del mismo contenido (`Clase 5.md`, `Clase 5 1.md` y `clase_5_1.pdf`); se ingesta una sola.

## Aportes propios de estas notas (no presentes en las diapositivas)

### Caché y latencia de memoria
- La RAM está fuera de la CPU: aun a velocidad cercana a la luz, el viaje por el bus produce **latencia** y deja al procesador ocioso.
- La **caché** mitiga esto trayendo bloques completos: **cache hit** (dato presente) vs. **cache miss** (hay que ir a RAM); sirve como *scratch pad* para valores intermedios.
- **Dirty bit**: marca bloques de caché modificados que deben escribirse a RAM antes de ser reemplazados (coherencia). Incorporado a [[conceptos/componentes-de-la-cpu]].

### Técnicas modernas del pipeline
- **Prefetching**, **predicción de saltos** (especulación: si la CPU adivina mal, descarta el pipeline) y **ejecución fuera de orden** — incorporadas a [[conceptos/pipelining-y-superescalaridad]].
- Requisito de diseño: instrucciones de **tamaño uniforme** hacen predecibles los tiempos de etapa.
- Métrica **FLOPS** (operaciones de punto flotante por segundo).

### Profundización CISC/RISC
- **Regla 80/20**: ~80% de las operaciones son simples; RISC (impulsado por IBM y universidades en los 90; AS400, PowerPC) optimiza ese 80%.
- Historia del **coprocesador**: en el 386 el punto flotante iba en un chip aparte; el 486 lo integró; hoy x86 maneja >2.000 instrucciones.
- **Límite térmico (~2014)** → núcleos heterogéneos (*efficiency/performance cores*, ej. Apple M1); convergencia CISC/RISC.
- **Modelo de negocio de [[entidades/arm|ARM]]**: diseña y licencia, no fabrica; Samsung y otros adaptan los diseños por gama.
- **Incompatibilidad de ISA**: un SO compilado para x86 no corre nativo en ARM (emuladores median con pérdida de rendimiento).
- Nomenclatura de palabra: x86 word=16 bits, dword=32, qword=64; ARM half word=16, word=32, dword=64.
- Todo incorporado a [[conceptos/cisc-y-risc]].

### Criterios de examen
- Del parcial (~5 puntos), ~3 se estiman sobre sistemas numéricos y [[conceptos/representacion-numeros-enteros|de representación]].
- La justificación de overflow **por regla de signos** es válida en examen ([[conceptos/flags-del-procesador]]).
- Caso especial: **−128 solo es representable en Ca2** con 8 bits.

## Contenido que repite las diapositivas
Repaso de conversiones, rangos BSS/MyS/Ca1/Ca2, flags con ejercicios, exceso, IEEE 754 (con la fórmula general `(−1)^S × 1,M × 2^(E−bias)`), casos de overflow (año 2038, GPS, Pac-Man, Ariane), pipelining y tabla CISC vs RISC.

## Referencias
- Archivo original: `Clase 5.md` (+ duplicados `Clase 5 1.md`, `clase_5_1.pdf`), movidos a `raw/assets/Arquitectura de Computadoras/`
