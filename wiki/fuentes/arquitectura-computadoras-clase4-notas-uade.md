---
titulo: "Arquitectura de Computadoras — Clase 4: Notas de clase (UADE)"
tipo: fuente
creado: 2026-09-15
actualizado: 2026-09-15
tags: [arquitectura-de-computadoras, uade, representacion, flags, notas-de-clase]
---

# Clase 4: Notas de clase (UADE)

Notas HoverNotes de la grabación de la clase del **2026-08-25** del curso de Arquitectura de Computadoras de [[entidades/uade]]. Complementan las diapositivas de [[fuentes/arquitectura-computadoras-clase4-uade]] con el desarrollo oral del docente. Existían dos copias idénticas (`Clase 4.md` y `Clase 4 1.md`); se ingesta una sola.

## Aportes propios de estas notas (no presentes en las diapositivas)

### Sistema numérico vs. sistema de representación
- El **sistema numérico** define símbolos y reglas (base); el **sistema de representación** es el contexto que da significado a los bits.
- **Polisemia del binario**: una misma cadena de bits significa valores distintos según se interprete como BSS, MyS, Ca1 o Ca2 — análogo a que "14" puede ser kilos, horas o grados. Ver [[conceptos/representacion-numeros-enteros]].
- La representación dentro de cada sistema es **unívoca** (salvo el doble cero de MyS/Ca1, defecto que motiva el Ca2).

### Por qué existen los complementos
- **La ALU solo sabe sumar**: la resta se transforma en suma del complemento (`10 − 5` → `10 + (−5)` en Ca2), permitiendo un único datapath para sumas y restas.
- Regla de consistencia: todos los operandos deben estar en el **mismo sistema** antes de operar.

### Detección intuitiva de overflow (regla de los signos)
- `(+) + (+) = (−)` → overflow; `(−) + (−) = (+)` → overflow.
- Incorporada a [[conceptos/flags-del-procesador]]. El carry sobrante de una suma se captura en el registro de estado; no forma parte del resultado.

### Momento de atención de interrupciones
- El procesador chequea [[conceptos/interrupciones|interrupciones]] pendientes **entre el write-back y el próximo fetch** del ciclo de instrucción.

### Criterios de examen y método de estudio
- En evaluaciones se exige **justificar cada resultado con el análisis de flags** (C, Z, N, V) y explicitar el sistema de representación y la base (`85₁₀` vs `85₈`).
- Distinguir **resultado aritmético puro** (todos los bits necesarios) vs. **resultado de procesador** (limitado al ancho del registro + carry flag).
- Metodología del TP: usar la guía de estudio y la IA de forma iterativa para comprender y debatir, no para resolver directamente.

## Contenido que repite las diapositivas
Repaso de ciclo de instrucción, Northbridge/Southbridge, conversiones entre bases (binario como puente), suma binaria y acarreo, BCD, rangos de BSS/MyS/Ca1/Ca2, y ejercicios de flags — ya cubiertos en [[fuentes/arquitectura-computadoras-clase4-uade]] y sus conceptos.

## Referencias
- Archivo original: `Clase 4.md` (+ duplicado `Clase 4 1.md`), movidos a `raw/assets/Arquitectura de Computadoras/`
