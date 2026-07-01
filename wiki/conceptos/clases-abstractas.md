---
titulo: "Clases Abstractas y Operaciones Abstractas"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [clase-abstracta, operacion-abstracta, herencia, poo, uml]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Clases Abstractas y Operaciones Abstractas

Una **clase abstracta** es una clase que **no puede tener instancias propias** — describe atributos y comportamientos comunes a un conjunto de subclases, dejando algunos aspectos de su funcionamiento sin definir, para que cada subclase concreta los implemente a su modo. Forma parte del esquema de [[conceptos/herencia|herencia]] como capa superior de superclases que captura lo común.

## Notación
El nombre de una clase abstracta se escribe **en cursiva**, o se añade la etiqueta `{abstract}` debajo del nombre en el compartimento de la clase — ver [[conceptos/uml-diagrama-de-clases]] para la notación general de clases.

## Operación abstracta
Una **operación abstracta** solo declara su signatura (nombre, parámetros, tipo de retorno) sin proporcionar implementación — se marca con `{abstract}` a continuación del prototipo. **Una clase con al menos una operación abstracta es, por definición, abstracta.**

Cualquier subclase concreta que herede de una clase con operaciones abstractas **debe implementarlas** (o volver a declararlas como abstractas, propagando la obligación más abajo en la jerarquía).

## Ejemplo
`Vehículo` (abstracta) declara la operación abstracta `conducir()`. Sus subclases `Coche` y `Barco` heredan esa operación pero cada una la implementa de forma distinta: en `Coche`, `conducir()` mueve las ruedas; en `Barco`, mueve el barco mediante sus propulsores. Ambas comparten la misma signatura pero distinta implementación — la base conceptual de lo que más adelante se formaliza como **polimorfismo**.

## Clase concreta y redefinición
Una **clase concreta** es lo opuesto a una abstracta: todas sus operaciones tienen implementación y se pueden instanciar objetos de ella. Una subclase puede:
- **Implementar** una operación abstracta heredada (proporcionarle cuerpo por primera vez), o
- **Redefinir** una operación ya concreta de la superclase (cambiar su comportamiento).

En ambos casos, la operación redefinida/implementada debe conservar la misma signatura (tipo de retorno, nombre, parámetros) que en la superclase. La redefinición aplica a todas las instancias de esa subclase.

## Por qué importa
Las clases abstractas permiten a quienes diseñan un modelo capturar el comportamiento común de una jerarquía sin comprometerse a una implementación única — cada subclase concreta resuelve el "cómo" mientras la superclase abstracta fija el "qué". Es la base estructural sobre la que luego se apoya el polimorfismo dinámico (resolución en tiempo de ejecución de qué implementación se ejecuta).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/herencia]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/uml-diagrama-de-clases]]
