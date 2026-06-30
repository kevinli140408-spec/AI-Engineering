---
titulo: "Programación Orientada a Objetos (POO)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [poo, objetos, clases, herencia, polimorfismo, uml]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Programación Orientada a Objetos (POO)

Paradigma (ver [[conceptos/paradigmas-de-programacion]]) que combina en una sola unidad — el **objeto** — tanto los datos como las funciones que operan sobre ellos, en lugar de separarlos como en la [[conceptos/metodologia-de-la-programacion|programación estructurada]]. Surge de los **Tipos Abstractos de Datos (TAD)**, que los capítulos 15-17 del libro retoman formalmente con UML (pendientes de ingesta).

## Objeto y clase
- **Objeto**: entidad individual con **estado** (sus datos/atributos) y **comportamiento** (sus operaciones/métodos). Ejemplo: un auto concreto.
- **Clase**: descripción genérica de un conjunto de objetos similares — define qué datos y qué operaciones comparten. Es, en esencia, un tipo de dato definido por el programador.
- **Instancia**: un objeto concreto creado a partir de una clase (p. ej. el objeto `Toyota` es una instancia de la clase `Carro`).
- Llamar a una operación de un objeto se conoce como **enviar un mensaje** al objeto.

## Las cinco propiedades fundamentales

| Propiedad | Definición |
|---|---|
| **Abstracción** | Centrarse en los aspectos esenciales de un objeto (qué es/qué hace), ignorando los detalles internos de implementación. |
| **Encapsulamiento** | Agrupar datos y las operaciones relacionadas bajo una misma unidad (la clase). |
| **Ocultación de datos** | Los datos internos solo son accesibles a través de una interfaz bien definida (las funciones miembro/métodos), protegidos de modificación directa. |
| **Herencia** | Definir nuevas clases (**derivadas**) a partir de una **clase base**, heredando sus atributos/operaciones y añadiendo otras propias. Implementa la **generalización/especialización** (p. ej. `Mamífero` es una generalización de `Caballo`). |
| **Polimorfismo** | Una misma operación (incluso un operador, si está *sobrecargado*) se comporta de modo distinto según el objeto que la invoca — se resuelve en tiempo de ejecución. |

## Por qué importa
- **Reusabilidad**: una clase depurada se reutiliza en otros programas sin modificarla; con herencia, se extiende sin tocar el código original.
- **Modelado del mundo real**: objetos del programa (empleados, listas, ventanas, autos) corresponden directamente a objetos del dominio del problema, a diferencia del enfoque procedimental.

## Lenguajes orientados a objetos
C++ (extensión de C; encapsulamiento + herencia + polimorfismo), Smalltalk (uno de los primeros, puramente OO), Java y C# (herederos de C++/C, dominantes en la industria) — ver línea histórica en [[conceptos/paradigmas-de-programacion]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/paradigmas-de-programacion]]
- [[conceptos/algoritmo]]
