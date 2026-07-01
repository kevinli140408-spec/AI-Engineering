---
titulo: "Estructuras (Registros), Uniones y Enumeraciones"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [estructuras, registros, uniones, enumeraciones, estructuras-de-datos, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Estructuras (Registros), Uniones y Enumeraciones

## Estructuras / registros
A diferencia de un [[conceptos/arrays-vectores-matrices|array]] (homogéneo: todos sus elementos del mismo tipo), una **estructura** (o **registro**, *struct*/*record*) es una colección de datos **heterogénea**: agrupa **campos** de distinto tipo bajo un único nombre.

```
estructura Empleado
  cadena: nombre
  entero: id
  real: salario
  estructura Fecha
    entero: dia, mes, anio
  fin_estructura: fechaIngreso
fin_estructura
```

Las estructuras pueden **anidarse** (un campo puede ser a su vez otra estructura, como `Fecha` dentro de `Empleado` arriba). Se accede a un campo con notación de punto: `Empleado.nombre`.

Python no tiene un equivalente de bajo nivel idéntico en este curso (este curso no usa `class`/`dataclass`/`dict` con este propósito), pero conceptualmente un registro es similar a un diccionario con claves fijas o a una clase simple con solo atributos.

## Arrays de estructuras
Combina ambos conceptos: un array cuyos elementos son, cada uno, una estructura completa — la forma natural de modelar una **tabla** de registros (p. ej. una nómina de empleados, donde cada posición del array es un `Empleado`). Se accede con `nomina[i].salario`.

## Uniones
```
union TipoPeso
  entero: enKilos
  real: enLibras
fin_union
```
Una **unión** declara varios campos de distinto tipo que **comparten el mismo espacio de memoria** — solo uno está "activo" a la vez (a diferencia de una estructura, donde todos los campos coexisten simultáneamente, cada uno con su propio espacio). Se usa para ahorrar memoria cuando se sabe que en un momento dado solo uno de los tipos posibles es relevante (p. ej. un campo que puede representarse en kilos *o* en libras, nunca ambos a la vez). Un patrón común es combinarla con un campo "etiqueta" (*tag*) en una estructura externa que indique cuál de los campos de la unión está activo.

## Enumeraciones
```
enum Dias {LUNES, MARTES, MIERCOLES, JUEVES, VIERNES, SABADO, DOMINGO}
```
Un tipo **enumerado** define una variable cuyos valores posibles son una lista cerrada de constantes con nombre (internamente representadas como enteros consecutivos, 0, 1, 2...). Mejora la legibilidad frente a usar números "mágicos" sueltos (`dia = 1` vs. `dia = LUNES`). Se puede usar en asignaciones, comparaciones, estructuras `según_sea` (`switch`) y como contador de un bucle `desde`. Python no tiene `enum` como palabra reservada del lenguaje base (existe el módulo `enum.Enum` de la librería estándar, fuera del alcance de este curso).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/algoritmo]]
