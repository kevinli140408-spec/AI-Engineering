---
titulo: "Arquitectura de Von Neumann"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [hardware, arquitectura-von-neumann, historia-computacion]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Arquitectura de Von Neumann

Diseño de computadora propuesto en 1945-1946 por el matemático [[entidades/john-von-neumann|John von Neumann]], cuya característica definitoria es el **programa almacenado**: las instrucciones del programa y los datos que procesa residen juntos, codificados de la misma forma, en la misma memoria principal. Es el fundamento conceptual de la inmensa mayoría de las computadoras digitales actuales — ver desarrollo de sus componentes en [[conceptos/organizacion-de-computadoras]].

## Contraste histórico: antes de Von Neumann
Máquinas anteriores como el **ENIAC** (1946) no almacenaban el programa: se "programaban" físicamente, recableando paneles y ajustando interruptores para cada nueva tarea, un proceso lento y propenso a errores. La propuesta de von Neumann — codificar las instrucciones como datos numéricos almacenados en memoria — permitió que cambiar de programa fuera tan simple como cargar otro conjunto de datos, sin tocar el hardware.

## Los cinco componentes
1. **Dispositivos de entrada**.
2. **Unidad Central de Proceso (UCP)**: Unidad de Control (UC, dirige la ejecución) + Unidad Aritmético-Lógica (UAL, ejecuta cálculos/comparaciones).
3. **Memoria principal**: almacena programa y datos en ejecución.
4. **Memoria secundaria**: almacenamiento permanente.
5. **Dispositivos de salida**.

## El ciclo de instrucción
Consecuencia directa del programa almacenado: la UC repite indefinidamente un ciclo de **buscar** (fetch) la siguiente instrucción en memoria, **decodificarla** y **ejecutarla**, avanzando secuencialmente salvo que una instrucción de salto/bifurcación indique lo contrario — este ciclo fetch-decode-execute es lo que realmente ejecuta cualquier programa escrito en un [[conceptos/lenguajes-de-programacion|lenguaje de programación]] una vez traducido a código máquina.

## Limitación conocida: el "cuello de botella de Von Neumann"
Como programa y datos comparten el mismo bus de acceso a memoria, la UCP no puede leer una instrucción y un dato simultáneamente — un límite de rendimiento estructural que arquitecturas alternativas (como la arquitectura Harvard, con memorias separadas para instrucciones y datos, usada en muchos microcontroladores) evitan.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/organizacion-de-computadoras]]
- [[conceptos/lenguajes-de-programacion]]
- [[entidades/john-von-neumann]]
