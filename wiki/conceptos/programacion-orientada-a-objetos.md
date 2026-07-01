---
titulo: "Programación Orientada a Objetos (POO)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [poo, objetos, clases, herencia, polimorfismo, uml]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Programación Orientada a Objetos (POO)

Paradigma (ver [[conceptos/paradigmas-de-programacion]]) que combina en una sola unidad — el **objeto** — tanto los datos como las funciones que operan sobre ellos, en lugar de separarlos como en la [[conceptos/metodologia-de-la-programacion|programación estructurada]]. Esta separación procedimental tiene un problema de fondo: los datos globales son accesibles (y modificables) por cualquier función del programa, lo que dificulta razonar sobre el código a medida que crece; además modela mal entidades del mundo real, que naturalmente combinan atributos y comportamiento.

## Tipo Abstracto de Dato (TAD) y clase
Un **[[conceptos/tipo-abstracto-de-dato|Tipo Abstracto de Dato (TAD)]]** describe no solo los atributos de un dato sino también su **comportamiento** (operaciones permitidas) y, opcionalmente, los estados que puede tener. En programación orientada a objetos, el TAD se materializa con el término **clase**: una clase es la implementación concreta de un TAD.

## Objeto y clase
- **Objeto**: entidad individual con **estado** (sus datos/atributos), **comportamiento** (sus operaciones/métodos) e **identidad** (lo distingue de cualquier otro objeto, incluso si tuviera el mismo estado). Ejemplo: un auto concreto.
- **Clase**: descripción genérica de un conjunto de objetos similares — define qué datos y qué operaciones comparten. Es, en esencia, un tipo de dato definido por el programador.
- **Instancia**: un objeto concreto creado a partir de una clase (p. ej. el objeto `Toyota` es una instancia de la clase `Carro`).
- Llamar a una operación de un objeto se conoce como **enviar un mensaje** al objeto.

## Identificación y modelado de objetos
El libro propone un proceso de modelado en 4 pasos: (1) **identificar los objetos** del dominio del problema (personas, estructuras de datos, dispositivos, etc.); (2) **agruparlos en clases** según atributos/comportamiento compartido; (3) **identificar atributos y operaciones** de cada clase; (4) **identificar las relaciones** entre clases — ver [[conceptos/relaciones-entre-clases]] (dependencia, asociación, agregación/composición) y [[conceptos/herencia]] (generalización/especialización).

## Las cinco propiedades fundamentales

| Propiedad | Definición |
|---|---|
| **Abstracción** | Centrarse en los aspectos esenciales de un objeto (qué es/qué hace), ignorando los detalles internos de implementación — como el control remoto de un TV: se opera sin saber su circuitería interna. |
| **Encapsulamiento** | Agrupar datos y las operaciones relacionadas bajo una misma unidad (la clase), exponiendo solo una **interfaz** (como el panel de una lavadora) que actúa de contrato de servicio. |
| **Ocultación de datos** | Los datos internos solo son accesibles a través de la interfaz, protegidos de modificación directa. |
| **Herencia** | Definir nuevas clases (**derivadas/subclase**) a partir de una **clase base/superclase**, heredando sus atributos/operaciones y añadiendo otras propias. Implementa la relación **"es-un"** (generalización/especialización; p. ej. `Mamífero` es una generalización de `Caballo`) — desarrollo completo en [[conceptos/herencia]]. |
| **Polimorfismo** | Una misma operación (incluso un operador, si está *sobrecargado*) se comporta de modo distinto según el objeto que la invoca — se resuelve en tiempo de ejecución mediante **ligadura dinámica**. |

## Por qué importa
- **Reusabilidad**: una clase depurada se reutiliza en otros programas sin modificarla (p. ej. plantillas/templates y la STL de C++); con herencia, se extiende sin tocar el código original.
- **Modelado del mundo real**: objetos del programa (empleados, listas, ventanas, autos) corresponden directamente a objetos del dominio del problema, a diferencia del enfoque procedimental.

## Lenguajes orientados a objetos
C++ (extensión de C; encapsulamiento + herencia + polimorfismo), Smalltalk (uno de los primeros, puramente OO), Java y C# (herederos de C++/C, dominantes en la industria) — ver línea histórica en [[conceptos/paradigmas-de-programacion]]. La terminología varía entre lenguajes (p. ej. Eiffel llama "rutina" al método y "ascendiente/descendiente" a superclase/subclase).

## Modelado con UML
A partir del Cap. 15, el libro adopta **UML** como notación estándar para diagramar clases y sus relaciones — ver [[conceptos/uml]] y, para la notación gráfica concreta de objetos/clases (visibilidad, compartimentos, declaración), [[conceptos/uml-diagrama-de-clases]].

## Ciclo de vida del objeto
La creación y destrucción de un objeto se gestiona con métodos especiales — ver [[conceptos/constructores-destructores]] para constructores, destructores y recolección de basura.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/paradigmas-de-programacion]]
- [[conceptos/algoritmo]]
- [[conceptos/uml]]
- [[conceptos/uml-diagrama-de-clases]]
- [[conceptos/constructores-destructores]]
- [[conceptos/relaciones-entre-clases]]
- [[conceptos/herencia]]
- [[conceptos/clases-abstractas]]
- [[conceptos/tipo-abstracto-de-dato]]
