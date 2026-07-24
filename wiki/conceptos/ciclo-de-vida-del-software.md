---
titulo: "Ciclo de Vida del Software"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-24
tags: [ciclo-de-vida, ingenieria-de-software, modelo-en-cascada, proceso-unificado, uml]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, teoria-sistemas-clase6-uade]
---

# Ciclo de Vida del Software

Secuencia de etapas por las que pasa un producto de software desde su concepción hasta su retirada de uso. Es el marco formal de la **ingeniería del software** (programación a gran escala, con equipos y proyectos de más de 100.000 líneas de código), a diferencia de la programación a pequeña escala que resuelve [[conceptos/metodologia-de-la-programacion|el proceso de resolución de un problema]] individual.

## Modelo en cascada
Modelo tradicional y más simple: ejecuta las actividades de forma secuencial, la salida de una etapa es la entrada de la siguiente.

1. **Análisis** — se subdivide en *análisis de requisitos* (definir qué debe hacer el sistema mediante un documento de especificaciones: entradas, salidas, casos especiales, mensajes de error) y *análisis* propiamente dicho (entradas/salidas e interacción con el usuario). Un prototipo simple del sistema suele ayudar a validar la especificación con el usuario antes de invertir en la implementación completa.
2. **Diseño** — determina *cómo* construir lo que el análisis definió: arquitectura del sistema (componentes, interfaces, relaciones — **diseño arquitectónico**) y luego algoritmos/estructuras de datos concretos de cada módulo (**diseño detallado**), usando precondiciones/postcondiciones para especificar cada módulo. Puede abordarse con diseño descendente (orientado a procesos) o diseño orientado a objetos (identifica primero los objetos y sus interacciones) — ver [[conceptos/principios-diseno-software]].
3. **Implementación (construcción)** — traduce el diseño a código en un lenguaje concreto.
4. **Pruebas (testing)** — comprueba que el sistema cumple los requisitos — ver [[conceptos/depuracion-y-pruebas]].
5. **Instalación (despliegue)** — entrega e instalación en el cliente.
6. **Mantenimiento** — corrección de fallos (*correctivo*) y adaptación a cambios del entorno (*adaptativo*).

Pressman y Sommerville nombran las etapas de forma distinta (p. ej. Pressman: Requisitos/Planeación/Modelado/Construcción/Despliegue; Sommerville: Ingeniería de sistemas/Análisis de requisitos/Diseño/Construcción/Instalación), pero el resultado es equivalente.

### Críticas al modelo en cascada
- Los proyectos reales rara vez son puramente secuenciales: las fases se solapan y hay que repetir actividades.
- Las iteraciones son casi inevitables: deficiencias del análisis de requisitos suelen aparecer recién en diseño, construcción o pruebas.
- Los requisitos cambian con el tiempo, y el modelo no da respuesta fácil a esos cambios ni a innovaciones tecnológicas.

Por esto el ciclo de vida real es **iterativo**, con bucles de realimentación entre etapas. Alternativas propuestas: prototipado, modelo iterativo e incremental, DRA (desarrollo rápido de aplicaciones), modelo en espiral, y el **Proceso Unificado**.

## Modelos de desarrollo (según el curso de Teoría de Sistemas)

El curso de Teoría de Sistemas de [[entidades/uade]] agrupa las alternativas al modelo en cascada puro en cuatro grandes familias: **modelo cascada**, **modelo evolutivo**, **modelo espiral** y **modelo incremental** — coincidiendo con las críticas y alternativas ya descriptas arriba, pero enmarcándolas explícitamente como aplicación de la [[conceptos/proceso-proyecto-modelo|distinción entre proceso, proyecto y modelo]] a la ingeniería de software. La elección entre ellos se vincula directamente con qué [[conceptos/metodologias-desarrollo-software|metodología de gestión]] (tradicional o ágil) se adopte para el proyecto.

## El Proceso Unificado (PU / USDP)
Basado en los trabajos de Jacobson, Booch y Rumbaugh (creadores de [[conceptos/uml|UML]]), enfatiza el desarrollo **iterativo e incremental**. Organiza el trabajo en **fases** (eje horizontal) y **flujos de trabajo** —análisis, diseño, implementación, pruebas— (eje vertical), donde cada iteración es una mini-cascada:

- **Incepción**: determina el ámbito y propósito del proyecto (mayor esfuerzo en requisitos).
- **Elaboración**: captura de requisitos y estructura del sistema (comienza diseño e implementación).
- **Construcción**: objetivo principal es construir el software (mayor esfuerzo en diseño/implementación).
- **Transición**: instalación y despliegue del producto.

Las pruebas se realizan en todas las fases salvo la incepción, con mayor peso en construcción y transición.

## Roles: cliente, desarrollador y usuario
- **Cliente**: individuo u organización que encarga el producto.
- **Desarrolladores**: equipo responsable de construirlo (desde requisitos o solo implementación).
- **Usuario**: quien finalmente usa el producto (puede coincidir con el cliente).

Si cliente y desarrolladores pertenecen a la misma organización, se habla de **software interno**; si son independientes, de **software por contrato**. En software comercial masivo (procesadores de texto, hojas de cálculo), el fabricante recupera el costo de desarrollo vendiendo grandes volúmenes de copias.

## Iteración, evolución y obsolescencia
Las etapas del ciclo de vida forman un bucle, no una lista lineal: el mantenimiento suele obligar a revisar especificaciones ya cerradas. La **documentación** actúa como núcleo que atraviesa todas las etapas (no es una etapa aislada). Con el tiempo, todo software tiende a la **obsolescencia**: llega un punto en que resulta más eficiente reescribirlo que seguir modificándolo, aunque mientras sea razonable modificarlo se prefiere esa vía por el alto costo de capital invertido.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/teoria-sistemas-clase6-uade]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/uml]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/proceso-proyecto-modelo]]
- [[conceptos/metodologias-desarrollo-software]]
