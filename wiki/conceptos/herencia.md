---
titulo: "Herencia: Generalización y Especialización"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [herencia, generalizacion, especializacion, uml, poo, herencia-multiple]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Herencia: Generalización y Especialización

La **herencia** es la implementación, a nivel de lenguaje de programación, del concepto UML de **generalización**: una relación entre un elemento general (**superclase**/clase base/padre) y un caso más concreto (**subclase**/clase derivada/hija). Es la manifestación más directa de la relación **es-un** (`Gato` es-un `Animal`) — ver [[conceptos/programacion-orientada-a-objetos]] para su rol entre las 5 propiedades fundamentales de la POO, y [[conceptos/relaciones-entre-clases]] para otras relaciones entre clases.

## Notación gráfica
Línea continua de la subclase a la superclase, terminada en un **triángulo abierto** que apunta a la superclase. Una generalización no lleva nombre ni multiplicidad, a diferencia de la asociación.

## Propiedades de la relación es-un
Es **transitiva** (si `C` deriva de `B` y `B` de `A`, entonces `C` es-un `A`), **asimétrica** (si `B` deriva de `A`, `A` no puede derivar de `B`) y **no reflexiva** (una clase no puede derivarse de sí misma). Una subclase hereda todos los atributos/operaciones de su(s) superclase(s) y puede añadir o redefinir los propios — esto reduce drásticamente el código redundante.

## Herencia simple vs. múltiple
- **Herencia simple**: una clase tiene exactamente un padre. Puede haber varios niveles (`Caballo` ← `Mamífero` ← `Animal`).
- **Herencia múltiple**: una clase hereda de dos o más clases base. Soportada por UML y [[entidades/lenguaje-c|C++]], **no por Java ni C#**, porque introduce **ambigüedad** cuando dos clases base comparten un atributo/operación con el mismo nombre (resoluble en C++ con el operador de ámbito `::`, p. ej. `v.Fuente::dimensionar()`).
- **Generalización múltiple**: una subclase puede descender de un único tipo genérico directo, pero los descendientes de un mismo nodo no son necesariamente mutuamente excluyentes (p. ej. `Gerente` e `Informático` pueden solaparse).

## Sintaxis de declaración
```
clase ClaseDerivada hereda_de [pública|privada|protegida] ClaseBase
  pública:
    // sección pública
  privada:
    // sección privada
fin_clase
```
Si se omite el especificador de acceso, la herencia es **privada por defecto** (cuidado: es la fuente más común de errores de "miembro inaccesible").

## Accesibilidad según tipo de herencia
| Tipo de herencia | público en base → | protegido en base → | privado en base → |
|---|---|---|---|
| **pública** | público | protegido | inaccesible |
| **protegida** | protegido | protegido | inaccesible |
| **privada** | privado | privado | inaccesible |

Una clase derivada **nunca** puede acceder a los miembros privados de su base, sin importar el tipo de herencia — por eso las clases base suelen usar `protegido` en vez de `privado` para los miembros que las derivadas sí necesitan tocar.

## Herencia múltiple: sintaxis
```
clase CDerivada hereda_de Base1, Base2, ...
```
El tipo de acceso se especifica por cada clase base individualmente; si se omite para alguna, esa base hereda de forma privada por defecto.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/relaciones-entre-clases]]
- [[conceptos/clases-abstractas]]
- [[conceptos/uml-diagrama-de-clases]]
- [[entidades/lenguaje-c]]
