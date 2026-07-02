---
titulo: "Verificación Formal"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [verificacion-formal, pruebas, precondiciones, postcondiciones]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Verificación Formal

Método para demostrar matemáticamente que un algoritmo cumple su especificación, en contraste con las [[conceptos/depuracion-y-pruebas|pruebas (testing)]], que solo pueden mostrar la **presencia** de errores ejecutando casos concretos, nunca demostrar su **ausencia** total.

## Cómo funciona
Parte de las **precondiciones** de un algoritmo o subprograma (lo que debe cumplirse antes de ejecutarlo, tratadas como axiomas) y, mediante reglas de inferencia lógica aplicadas paso a paso sobre cada sentencia del programa, demuestra que necesariamente se alcanzan las **postcondiciones** (lo que debe cumplirse al finalizar) — la misma noción de precondición/postcondición usada como técnica de "programación segura contra fallos" en [[conceptos/principios-diseno-software]].

Un **invariante** — condición que debe mantenerse verdadera en cada iteración de un bucle — cumple un rol equivalente dentro de estructuras repetitivas, y es también la herramienta práctica que se usa al depurar manualmente por aproximaciones sucesivas (ver [[conceptos/depuracion-y-pruebas]]).

## Alcance y limitaciones
- Funciona razonablemente bien en programas **pequeños y bien acotados**, donde el número de rutas lógicas es manejable.
- Se vuelve **extremadamente compleja** en programas grandes: el número de estados y rutas posibles crece de forma combinatoria, haciendo la demostración formal completa poco práctica.
- Por eso, en la práctica de la industria, la verificación formal se usa como **complemento** de las pruebas dinámicas (caja negra/caja blanca), no como reemplazo — se reserva típicamente para componentes críticos (seguridad, sistemas embebidos, protocolos) donde el costo de un error es inaceptablemente alto.

## Relación con Dijkstra
La idea de razonar sobre programas con precondiciones/postcondiciones como axiomas lógicos proviene del trabajo de [[entidades/edsger-dijkstra|Edsger W. Dijkstra]] y de la lógica de Hoare (tripletas `{P} S {Q}`), la misma tradición intelectual que motivó su crítica a la sentencia `goto` (ver [[conceptos/estructura-condicional]]) y su frase, citada en [[conceptos/depuracion-y-pruebas]], de que las pruebas nunca prueban la ausencia de errores — ver también [[conceptos/algoritmo-de-dijkstra]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/estructura-condicional]]
- [[conceptos/algoritmo-de-dijkstra]]
- [[entidades/edsger-dijkstra]]
