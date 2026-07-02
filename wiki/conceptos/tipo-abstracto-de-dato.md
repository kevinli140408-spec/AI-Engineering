---
titulo: "Tipo Abstracto de Dato (TAD)"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [tad, abstraccion-de-datos, clases, poo]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Tipo Abstracto de Dato (TAD)

Un **Tipo Abstracto de Dato (TAD)** es un modelo matemático de un dato que describe, además de los valores que puede tomar, su **comportamiento**: el conjunto de operaciones permitidas sobre él y, opcionalmente, los estados internos que puede alcanzar. La idea central es separar la **especificación** (qué operaciones existen y qué hacen) de la **implementación** (cómo se almacenan los datos y cómo se codifican esas operaciones) — es la base de la [[conceptos/principios-diseno-software|abstracción de datos]].

## Relación con la clase
En [[conceptos/programacion-orientada-a-objetos|programación orientada a objetos]], el TAD se materializa concretamente con el término **clase**: una clase es la implementación de un TAD en un lenguaje de programación específico. El TAD define el contrato ("qué hace"); la clase provee el código ("cómo lo hace"), oculto tras una interfaz.

Ejemplo clásico: el TAD "Pila" especifica operaciones como `apilar`, `desapilar` y `cima`, sin decir si internamente se implementa con un array o con una lista enlazada — ver [[conceptos/pilas-y-colas]]. Cualquier estructura que cumpla ese contrato es una implementación válida del TAD, intercambiable sin afectar al código que la usa.

## Por qué importa
- **Ocultación de información**: el usuario del TAD solo necesita conocer su interfaz (las operaciones disponibles), no los detalles de almacenamiento — permite cambiar la implementación sin romper el código cliente.
- **Reutilización**: al depender solo del contrato, un mismo TAD puede reimplementarse con distintas estructuras de datos según el contexto (eficiencia en tiempo vs. espacio).
- **Base de la abstracción de datos**: en [[conceptos/principios-diseno-software]], la abstracción de datos se define precisamente como centrarse en las operaciones sobre un TAD en vez de en su representación interna (p. ej. usar `string` en C++ sin conocer cómo almacena los caracteres).

## Ejemplos en el libro
Los TAD más comunes tratados en capítulos de estructuras de datos son [[conceptos/pilas-y-colas|pilas y colas]] (LIFO/FIFO), [[conceptos/listas-enlazadas|listas enlazadas]], [[conceptos/arboles|árboles]] y [[conceptos/grafos]] — cada uno definido primero por su comportamiento y luego implementado con arrays, punteros o registros.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/pilas-y-colas]]
- [[conceptos/listas-enlazadas]]
