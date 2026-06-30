---
titulo: "Algoritmo"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [algoritmo, pseudocodigo, diagramas-de-flujo]
fuentes: [pensamiento-computacional-mm, guia-estudio-algoritmia-mm]
---

# Algoritmo

**Secuencia finita, repetible y correcta de pasos** (instrucciones) que llevan a la solución de un problema dado. Puede haber varios algoritmos válidos para un mismo problema.

## Características
- **Secuencia**: el orden de los pasos importa.
- **Finita**: debe tener un final.
- **Repetible**: con los mismos datos de entrada, el resultado debe ser siempre el mismo.
- **Correcto**: debe resolver el problema para el que fue diseñado.

## Formas de representación

### Pseudocódigo
Instrucciones escritas en lenguaje informal (vocabulario cotidiano), facilitando su traducción posterior a un [[entidades/python|lenguaje de programación]].

### Diagramas
- **Diagrama de flujo**: el más difundido; usa símbolos estandarizados (óvalos, rectángulos, rombos, flechas). Ventaja: visual e intuitivo. Desventaja: difícil de leer en algoritmos grandes. Se usa la herramienta *Flowgorithm*.
- **Estructograma (Chapin/Nassi-Shneiderman)**: bloques anidados sin flechas; fomenta programación estructurada.
- **Diagramas de actividad (UML)**: para sistemas más complejos.
- **Diagramas de estado**: modelan transiciones entre estados (semáforos, cajeros).

## Diseño de un algoritmo (guía)
1. Determinar el objetivo (entradas y salidas esperadas).
2. Identificar las variables necesarias para entrada y salida.
3. Pensar las instrucciones: lectura de entrada → procesamiento → salida.
4. **Prueba de escritorio**: seguir el algoritmo paso a paso con datos de ejemplo para verificar que cumple el objetivo.
5. Traducir a [[entidades/python|Python]] y depurar.

## Algoritmo vs. lenguaje vs. computadora
> "En la ciencia de la computación y en la programación, los algoritmos son más importantes que los lenguajes de programación o las computadoras." (Joyanes Aguilar)

Un lenguaje de programación es solo un medio para expresar un algoritmo; la computadora es solo el procesador que lo ejecuta.

## Referencias

- [[fuentes/pensamiento-computacional-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[conceptos/pensamiento-computacional]]
- [[conceptos/lenguajes-de-programacion]]
