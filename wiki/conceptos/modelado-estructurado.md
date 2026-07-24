---
titulo: "Modelado Estructurado (Análisis Estructurado)"
tipo: concepto
creado: 2026-07-24
actualizado: 2026-07-24
tags: [teoria-de-sistemas, ingenieria-de-software, analisis-estructurado, dfd, der]
fuentes: [teoria-sistemas-clase6-uade]
---

# Metodología de Análisis Estructurada

Conjunto de métodos orientados a analizar y convertir requisitos de negocio en especificaciones y, en última instancia, en programas informáticos, configuraciones de hardware y procedimientos manuales relacionados. El **modelo esencial** es un grupo de diagramas que modelan un sistema.

## Modelo ambiental

Define la frontera entre el sistema y el resto del mundo (ambiente, entorno o contexto). Consiste en una descripción breve del propósito del sistema, una lista de acontecimientos/eventos y un diagrama de contexto. Especifica claramente qué es parte del sistema y qué no. Elementos del diagrama de contexto: **entidades (actores)** y **relaciones (flujos)**.

1. **Declaración de propósito**: declaración textual breve y concisa del propósito del sistema, dirigida a niveles no técnicos.
2. **Lista de acontecimientos**: lista narrativa de los estímulos externos a los que el sistema debe responder (marcados F=flujo, T=temporal, C=control).
3. **Diagrama de contexto**: caso especial de [[conceptos/modelado-estructurado|diagrama de flujo de datos]] donde una sola burbuja representa todo el sistema, mostrando terminadores (personas/organizaciones/sistemas externos), datos de entrada/salida, almacenes de datos compartidos y la frontera del sistema.

## Modelo de comportamiento

Describe el comportamiento que el sistema debe tener para interactuar exitosamente con el entorno. Se compone de:

### Diagrama de Flujo de Datos (DFD)
Representación gráfica del flujo de datos a través de un sistema de información; ayuda a visualizar cómo resultarán los datos y su efecto sobre la estructura de todo el sistema.

### Diagrama Entidad-Relación (DER)
Herramienta para el modelo de datos que facilita la representación de entidades de una base de datos. Tipos de relaciones: **1:1** (uno a uno), **1:N** (uno a varios), **N:1** (varios a uno), **N:M** (varios a varios).

### Diagrama de Transición de Estados
Muestra el comportamiento dependiente del tiempo de un sistema de información: los estados que puede tomar un componente o sistema y los eventos que implican el cambio de un estado a otro. El estado inicial se representa con un círculo relleno; el estado final, con un círculo relleno rodeado de una circunferencia.

## Relación con otros paradigmas

Se contrasta con el paradigma orientado a objetos (ver [[conceptos/programacion-orientada-a-objetos]] y [[conceptos/uml-diagrama-de-clases]]) como alternativa de modelado de sistemas de software.

## Referencias
- [[fuentes/teoria-sistemas-clase6-uade]]
- [[conceptos/proceso-proyecto-modelo]]
- [[conceptos/metodologias-desarrollo-software]]
- [[conceptos/programacion-orientada-a-objetos]]
