---
titulo: "Algoritmo"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-10-24
tags: [algoritmos, pseudocodigo, diagramas-de-flujo]
fuentes: [pensamiento-computacional-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
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
- **Lógicos**: el programa corre sin errores de compilación ni ejecución, pero produce resultados incorrectos; los más difíciles de detectar — obligan a revisar el diseño del algoritmo. Ver proceso completo en [[conceptos/metodologia-de-la-programacion]] y técnicas de depuración y pruebas en [[conceptos/depuracion-y-pruebas]].

## Algoritmo vs. lenguaje vs. computadora
> "En la ciencia de la computación y en la programación, los algoritmos son más importantes que los lenguajes de programación o las computadoras." (Joyanes Aguilar)

Un lenguaje de programación es solo un medio para expresar un algoritmo; la computadora es solo el procesador que lo ejecuta. Un algoritmo es **independiente del lenguaje**: describe un procedimiento que puede implementarse en cualquier lenguaje de propósito general, o incluso ejecutarse a mano con lápiz y papel ([[fuentes/introduccion-a-la-programacion-con-python-3]]).

## Las 5 propiedades formales de un algoritmo
No cualquier procedimiento paso a paso es un algoritmo. Marzal, Gracia y García ([[fuentes/introduccion-a-la-programacion-con-python-3]]) formalizan la definición con la analogía de una receta de cocina (freír un huevo) para mostrar, por eliminación, qué falla en una receta mal escrita:

1. **Entrada**: cero o más datos de entrada (los "ingredientes" — deben ser precisos: ¿qué tipo de huevo?, ¿cuánta sal?).
2. **Salida**: uno o más datos de salida como resultado (la "presentación" del plato).
3. **Precisión**: cada paso debe estar definido con exactitud, sin ambigüedad (no vale "romper la cáscara con el poder de la mente"; cada paso debe ser realizable, y no debe incluir pasos irrelevantes que no acerquen al objetivo, como "sintonizar la radio").
4. **Finitud**: debe terminar tras un número finito de pasos.
5. **Efectividad**: cada paso debe poder ejecutarse en tiempo finito con los recursos disponibles. Una secuencia puede tener todos los pasos de duración finita y aun así no garantizar terminación en tiempo razonable (ejemplo clásico: "comprar lotería → esperar sorteo → si no ganás, repetir" es finito en cada paso pero no efectivo como método para hacerse millonario).

## Origen histórico del término
La palabra "algoritmo" proviene de **Al-Juarismi** (Abu Ja'far Mohammed ibn Mûsâ Al-Khowârizmi), matemático persa del siglo IX que introdujo el sistema de numeración hindú en el mundo árabe y, vía traducciones latinas medievales ("Dixit Algorismi..."), en Occidente. El concepto en sí es anterior: en el siglo III a.C., **Euclides** propuso en su obra *Elementos* un método sistemático para calcular el Máximo Común Divisor de dos números — el "algoritmo de Euclides", que sigue siendo el ejemplo canónico de algoritmo recursivo/iterativo bien definido.

## Referencias

- [[fuentes/pensamiento-computacional-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/pensamiento-computacional]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/depuracion-y-pruebas]]
