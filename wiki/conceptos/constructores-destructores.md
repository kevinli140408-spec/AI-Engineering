---
titulo: "Constructores y Destructores"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [constructores, destructores, recoleccion-de-basura, poo, cpp, java, csharp]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Constructores y Destructores

Métodos especiales ligados al ciclo de vida de un [[conceptos/programacion-orientada-a-objetos|objeto]], invocados automáticamente al crearse y destruirse.

## Constructor
- Mismo nombre que la clase; **sin tipo de retorno** (ni siquiera `void`); puede tener cero o más parámetros.
- Se invoca automáticamente al crear un objeto (instanciación), p. ej. `Rectangulo Rect(25, 25, 75, 75);` o con `new`: `Rectangulo *Crect = new Rectangulo(25, 25, 75, 75);`.
- **Constructor por defecto**: sin parámetros; si la clase no declara ningún constructor, el compilador genera uno automáticamente (pero sin garantía de inicializar los datos a valores predecibles — buena práctica: escribirlo explícitamente).
- Una clase puede tener **múltiples constructores sobrecargados**, distinguidos por su lista de parámetros.
- Cuidado: `Punto P();` no llama al constructor por defecto — declara una función `P` que devuelve `Punto`.

## Destructor
- Mismo nombre que la clase, precedido de `~` (C++/C#) o la palabra `destructor` (pseudocódigo); **sin retorno ni parámetros**.
- A diferencia del constructor, **solo puede existir un destructor por clase**.
- Se invoca automáticamente cuando el objeto sale de ámbito o se destruye explícitamente.
- En **C++**: liberación manual con `delete`; el destructor se llama al terminar el bloque (ámbito local), al finalizar `main()` (ámbito de archivo) o al ejecutar `delete` (objetos dinámicos) — el programador controla totalmente cuándo ocurre.
- En **Java y C#**: no hay liberación manual; un **recolector de basura (Garbage Collector)** libera memoria automáticamente cuando detecta que ya no existen referencias a un objeto, en un momento no determinista. Java no tiene destructores propiamente — el método `finalize()` cumple un rol similar (ejecuta limpieza antes de que el recolector reclame el objeto), pero **no hay garantía de cuándo —ni si— se ejecutará**, por lo que no debe ser la única vía de liberar recursos críticos. C# permite forzar la recolección con `GC.Collect()` y esperar con `GC.WaitForPendingFinalizers()`.

## Recolección de basura (garbage collection)
Técnica de Java/C# que evita la gestión manual de memoria: cuando ya no hay ninguna referencia activa a un objeto, su memoria queda disponible para ser reclamada; ocurre esporádicamente, no en el instante exacto en que el objeto deja de usarse. Contrasta con C++, donde cada `new` requiere su `delete` correspondiente — desarrollo completo (estrategias de implementación, trade-offs) en [[conceptos/recoleccion-de-basura]].

## Implementación en C++
- El código de las funciones miembro se guarda en archivos `.cpp`/`.cp`; la declaración de la clase va en un **archivo de cabecera** `.h`, incluido con `#include` — permite reutilizar la misma declaración en varios programas sin duplicarla.
- **Clases compuestas**: una clase cuyos miembros dato son a su vez objetos de otras clases. Antes de ejecutar el cuerpo del constructor de la clase compuesta, se construyen primero los miembros dato individuales, en su orden de declaración; los destructores se llaman, en general, en orden inverso (aunque en C++ el momento exacto lo determina el recolector cuando se usa asignación dinámica).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/uml-diagrama-de-clases]]
- [[conceptos/recoleccion-de-basura]]
