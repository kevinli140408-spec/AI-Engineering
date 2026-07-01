---
titulo: "Metodología de la Programación"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-01
tags: [metodologia, diseno-descendente, programacion-modular, programacion-estructurada]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Metodología de la Programación

Conjunto de fases que conducen de un problema a un programa que lo resuelve, aplicado de forma sistemática para todo [[conceptos/algoritmo|algoritmo]].

## Fases de resolución de un problema con computadora
1. **Análisis**: definir entradas, salida deseada y restricciones del problema.
2. **Diseño del algoritmo**: determinar *cómo* resolver lo que el análisis definió.
3. **Codificación**: traducir el algoritmo a un [[conceptos/lenguajes-de-programacion|lenguaje de programación]] (programa fuente).
4. **Compilación y ejecución**: traducir y correr el programa.
5. **Verificación y depuración**: probar con datos de test (normales, extremos, especiales) y corregir errores — ver tipos de error en [[conceptos/algoritmo]].
6. **Mantenimiento**: actualizar el programa ante nuevas necesidades.
7. **Documentación**: interna (comentarios en el código) y externa (análisis, diagramas, manuales de usuario) — debe acompañar todas las fases anteriores.

## Diseño descendente y refinamiento sucesivo
El método dominante para diseñar algoritmos es **divide y vencerás** (*divide and conquer*): descomponer un problema complejo en subproblemas más simples, y estos a su vez en otros de nivel más bajo, hasta poder implementarlos directamente. Este proceso se llama **diseño descendente** (*top-down*) y la sucesiva adición de detalle en cada nivel, **refinamiento sucesivo** (*stepwise refinement*).

## Programación modular
Divide el programa en **módulos** independientes, cada uno con una única tarea, un solo punto de entrada y uno de salida. Un programa principal llama a subprogramas que a su vez pueden llamar a otros. Ventajas: módulos planeables/codificables/depurables por separado (incluso por distintos programadores), y modificables sin afectar al resto.

## Programación estructurada y sus límites
Lenguajes procedimentales (C, Pascal, FORTRAN) organizan el programa en funciones que manipulan **datos locales** (privados de la función) o **datos globales** (accesibles desde cualquier función). En programas grandes esto genera dos problemas:
- Las funciones tienen acceso ilimitado a datos globales → difícil de modificar sin romper otras funciones.
- Separar datos y funciones no modela bien los objetos del mundo real (que tienen atributos *y* comportamiento juntos).

Esta limitación es la motivación directa de la [[conceptos/programacion-orientada-a-objetos|Programación Orientada a Objetos]].

## De la programación individual a la ingeniería de software
Las 7 fases anteriores describen la programación a pequeña escala. Cuando el proyecto es grande (equipos de programadores, +100.000 líneas de código) estas fases se formalizan como el [[conceptos/ciclo-de-vida-del-software|ciclo de vida del software]] (modelo en cascada, Proceso Unificado), y se rigen por un conjunto más amplio de [[conceptos/principios-diseno-software|principios de diseño de software]], [[conceptos/estilo-y-documentacion|reglas de estilo y documentación]] y técnicas de [[conceptos/depuracion-y-pruebas|depuración y pruebas]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/algoritmo]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/ciclo-de-vida-del-software]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/estilo-y-documentacion]]
- [[conceptos/depuracion-y-pruebas]]
