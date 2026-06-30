---
titulo: "Algoritmo"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [algoritmo, pseudocodigo, diagramas-de-flujo]
fuentes: [pensamiento-computacional-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion]
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
Instrucciones escritas en lenguaje informal (vocabulario cotidiano), facilitando su traducción posterior a un [[entidades/python|lenguaje de programación]]. No es ejecutable por una computadora; es un borrador que permite concentrarse en la lógica sin las reglas estrictas de un lenguaje concreto. Convención en español (Joyanes Aguilar): `inicio`/`fin`, `leer`/`escribir`, `si-entonces-si_no`, `mientras-fin_mientras`, `repetir-hasta_que` — equivalentes a `start`/`end`, `read`/`write`, `if-then-else`, `while-end`, `repeat-until` en inglés.

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

## Estructura formal de un algoritmo (pseudocódigo)
```
algoritmo nombre          // cabecera
var tipo: lista_variables // sección de declaración
const nombre = valor
inicio
  <instrucciones>         // cuerpo del algoritmo
fin
```
Comentarios: `//` (línea) o `/* */` (multilínea) en notación tipo C; `{ }` en Pascal. Ver tipos de operadores y expresiones usadas en las instrucciones en [[conceptos/operadores-y-expresiones]].

## Tipos de errores al ejecutar un programa
- **De compilación**: uso incorrecto de las reglas del lenguaje (errores de sintaxis); el compilador no genera el programa objeto.
- **De ejecución**: instrucciones comprensibles pero no ejecutables (p. ej. división por cero); detienen el programa con un mensaje de error.
- **Lógicos**: el programa corre sin errores de compilación ni ejecución, pero produce resultados incorrectos; los más difíciles de detectar — obligan a revisar el diseño del algoritmo. Ver proceso completo en [[conceptos/metodologia-de-la-programacion]].

## Algoritmo vs. lenguaje vs. computadora
> "En la ciencia de la computación y en la programación, los algoritmos son más importantes que los lenguajes de programación o las computadoras." (Joyanes Aguilar)

Un lenguaje de programación es solo un medio para expresar un algoritmo; la computadora es solo el procesador que lo ejecuta.

## Referencias

- [[fuentes/pensamiento-computacional-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[conceptos/pensamiento-computacional]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
