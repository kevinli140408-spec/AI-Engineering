---
titulo: "Depuración y Pruebas (Testing)"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [depuracion, pruebas, testing, caja-negra, caja-blanca, verificacion]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
---

# Depuración y Pruebas (Testing)

**Pruebas** (testing) y **depuración** (debugging) suelen confundirse pero son distintas: las pruebas determinan *si* un programa funciona correctamente; la depuración es la actividad posterior de *encontrar y eliminar* los errores que las pruebas revelaron. Como resume Dijkstra: las pruebas muestran la presencia de errores, nunca pueden demostrar su ausencia (la prueba exhaustiva de todos los casos posibles es, en la práctica, imposible).

## Tipos de error
Clasificación básica ya vista en [[conceptos/algoritmo]] (compilación/sintaxis, ejecución, lógicos); aquí se profundiza:
- **Errores de sintaxis (compilación)**: puntuación incorrecta, palabras mal escritas, palabras reservadas ausentes — el compilador los detecta y el programa no se traduce.
- **Errores en tiempo de ejecución**: la sentencia es válida pero pide algo imposible (división por cero, índice de array fuera de rango) — solo se detectan al ejecutar.
- **Errores lógicos**: el programa corre y produce una respuesta, pero es incorrecta (p. ej. un bucle `desde 0 hasta 10` que en realidad recorre 11 valores, o `+` escrito donde iba `*`) — los más difíciles de detectar porque no hay ningún mensaje de error.

## Técnicas de depuración
- **Puntos de ruptura (breakpoints)**: detienen la ejecución en un punto concreto para inspeccionar el estado.
- **Inspecciones/observaciones (watches)**: examinan el valor de una variable específica durante la ejecución.
- **Sentencias `escribir` temporales**: informan sobre valores y la posición del programa donde ocurren.
- Ubicaciones estratégicas: al entrar/salir de estructuras `si-entonces-sino`, al principio/final de bucles, y al principio/final de subprogramas (donde se examinan los parámetros).
- La clave es usar **invariantes** (condiciones que deben ser verdaderas en un punto dado) para localizar, por aproximaciones sucesivas, la primera posición donde la condición esperada deja de cumplirse.
- En equipos de programación, un miembro suele actuar de **bibliotecario**: controla qué versión de cada procedimiento está vigente en la librería compartida.

## Filosofía y selección de datos de prueba
Principios: suponer que el programa tiene errores hasta probar lo contrario; ningún test aislado prueba ausencia de errores; empezar las pruebas antes de terminar de codificar; cambiar solo una cosa a la vez. Buenos datos de prueba deben (1) tener una salida correcta conocida de antemano y (2) incluir las entradas con mayor probabilidad de producir errores — en particular **valores extremos o límite** (los bordes de un rango válido, p. ej. 0 y 23 para una hora del día) y asegurar que cada línea de código, y cada rama que a veces se salta por completo, se ejecute al menos una vez en algún caso de prueba.

## Técnicas de prueba
- **Prueba de ruta básica**: un conjunto de datos que garantiza que cada sentencia se ejecuta al menos una vez (apoyada en teoría de grafos).
- **Caja negra**: prueba desde la interfaz/el punto de vista del usuario, sin conocer la implementación — verifica que el software cumple su función correctamente.
- **Caja blanca**: conoce la implementación y prueba las rutas lógicas internas con casos que cubren condiciones y bucles específicos.
- **Niveles de prueba**: de módulo/clase (caja blanca, por quien lo implementó), de integración (caja negra, interacción entre módulos), de aplicación (por quien hizo el análisis) y **beta** (versión preliminar entregada a usuarios expertos antes del lanzamiento final).
- **Principio de Pareto**: el 80% de los errores suele concentrarse en el 20% de los módulos — conviene identificarlos y probarlos con más profundidad que al resto.
- Reglas de Davis: toda prueba debe ser rastreable a un requisito del cliente; se planean con anticipación; progresan de lo pequeño a lo grande; la prueba exhaustiva no es posible.

## Verificación formal
Método complementario a las pruebas: usa reglas matemáticas para demostrar que un algoritmo cumple su especificación, partiendo de las **precondiciones** (como axiomas) y mostrando que los pasos conducen a las **postcondiciones**. Funciona bien en programas pequeños pero es muy compleja en programas grandes — desarrollo completo en [[conceptos/verificacion-formal]].

## El depurador
Un Entorno Integrado de Desarrollo (EID) incluye un depurador que permite ejecutar el programa sentencia a sentencia, insertar breakpoints, y observar/trazar variables — herramienta central para aplicar en la práctica las técnicas anteriores.

## Traza de ejecución
Técnica manual (sin depurador) para entender o depurar un programa: seguir el curso del programa línea a línea para una configuración concreta de datos de entrada, anotando qué sentencias se ejecutan y qué valor toma cada variable en cada paso ([[fuentes/introduccion-a-la-programacion-con-python-3]]). Es especialmente útil con estructuras condicionales, donde conviene trazar al menos un caso por cada rama posible para verificar que el programa hace lo esperado en todas ellas.

## Manejo de excepciones en Python (`try`/`except`)
Alternativa a comprobar errores por anticipado con `if` (lo que puede llenar el programa de comprobaciones): "intenta ejecutar este bloque y, si se produce un error, ejecuta este otro" — control **correctivo** en vez de preventivo. Desarrollo completo de la sintaxis (`except` múltiples, `else`, `finally`, `raise`, `assert`) en [[conceptos/manejo-de-excepciones]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/algoritmo]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/estilo-y-documentacion]]
- [[conceptos/ciclo-de-vida-del-software]]
- [[conceptos/verificacion-formal]]
- [[conceptos/manejo-de-excepciones]]
