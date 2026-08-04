---
titulo: "UML (Unified Modeling Language)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-28
tags: [uml, modelado, diagramas, poo, omg]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# UML (Unified Modeling Language)

**Lenguaje Unificado de Modelado**: lenguaje gráfico estándar para visualizar, especificar, construir y documentar los artefactos de un sistema de software, especialmente bajo el paradigma de la [[conceptos/programacion-orientada-a-objetos|programación orientada a objetos]]. No es un método ni un proceso de desarrollo en sí mismo — se usa *dentro* de un proceso de desarrollo iterativo, no lo reemplaza.

Como todo lenguaje, UML define:
- **Sintaxis**: notación gráfica (símbolos, formas, líneas).
- **Semántica**: el significado de cada símbolo.
- **Pragmática**: las reglas de uso correcto en contexto.

Un modelo UML captura dos dimensiones de un sistema: su **estructura estática** (clases, objetos, relaciones) y su **comportamiento dinámico** (interacciones, cambios de estado en el tiempo).

## Tipos de diagramas
**Estructurales** (la "foto fija" del sistema): diagrama de clases, de objetos, de componentes, de estructuras compuestas, de despliegue.

**De comportamiento** (cómo cambia/interactúa el sistema en el tiempo): diagrama de actividad, de comunicación, de interacción, de secuencia, de máquinas de estado, de tiempo, de casos de uso.

(El diagrama de clases —el más usado para diseño orientado a objetos— se desarrolla en detalle en [[conceptos/uml-diagrama-de-clases]] (Cap. 16); las relaciones entre clases —asociación, agregación, herencia— en el Cap. 17.)

## Por qué UML
Gestiona la complejidad del diseño de sistemas grandes mediante un lenguaje formal, conciso, comprensible y escalable, que encapsula "lecciones aprendidas" de décadas de ingeniería de software, respaldado como estándar por la **[[entidades/omg|OMG (Object Management Group)]]**.

## Historia
Antes de 1994 coexistían varios métodos de modelado orientado a objetos incompatibles entre sí: **OMT** ([[entidades/tres-amigos-uml|James Rumbaugh]]), **OOSE** (Ivar Jacobson, con énfasis en casos de uso) y **Booch'93** (Grady Booch), además de métodos como Coad/Yourdon y Fusion. La fragmentación dificultaba la comunicación entre equipos.

- **1994**: Rumbaugh se une a Booch en Rational; comienzan a unificar OMT y Booch'93 en un borrador llamado "Unified Method" (v0.8).
- **1995**: se les une Jacobson (autor de OOSE) — el trío pasa a conocerse como **"los tres amigos"**.
- **Enero 1997**: se publica **UML 1.0**.
- **1997**: la **[[entidades/omg|OMG]]** adopta UML como estándar (v1.1).
- **1998-2000**: versiones 1.2 a 1.4 (semántica de acción).
- **2004**: **UML 2.0**, revisión mayor.
- **Agosto 2007**: **UML 2.1.1**, versión vigente al momento de escribirse el libro.

UML 2 se especifica formalmente en 4 documentos de la OMG: *Diagram Interchange*, *UML Infrastructure*, *UML Superstructure* y *OCL* (Object Constraint Language).

### El futuro: MDA
La **Arquitectura Dirigida por Modelos (MDA, Model Driven Architecture)** propone usar modelos UML (incluyendo PSM, *Platform Specific Models*) como artefactos centrales del desarrollo, de los que el código se deriva en gran parte automáticamente — una dirección hacia la que apunta la evolución de UML.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/paradigmas-de-programacion]]
- [[entidades/omg]]
- [[entidades/tres-amigos-uml]]
