---
titulo: "Recolección de Basura (Garbage Collection)"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [recoleccion-de-basura, memoria, poo, java, csharp, python]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Recolección de Basura (Garbage Collection)

Técnica de gestión automática de memoria que libera el espacio ocupado por objetos que ya no tienen ninguna referencia activa en el programa, evitando que el programador tenga que liberar memoria manualmente — mencionada como parte del ciclo de vida del objeto en [[conceptos/constructores-destructores]].

## Por qué existe
En **C++**, cada objeto creado con `new` requiere un `delete` correspondiente y explícito; olvidarlo produce una **fuga de memoria (memory leak)**: memoria reservada que nunca se libera y se acumula mientras el programa corre. Lenguajes como **Java** y **C#** eliminan esta responsabilidad del programador con un **recolector de basura**, que detecta automáticamente los objetos inalcanzables y reclama su memoria en un momento no determinista (no necesariamente apenas el objeto deja de usarse).

## Estrategias comunes de implementación
Aunque el libro no entra en el detalle algorítmico, las técnicas estándar de la industria incluyen:
- **Conteo de referencias**: cada objeto lleva un contador de cuántas variables lo referencian; al llegar a cero, se libera de inmediato (usado por CPython, el intérprete de referencia de [[entidades/python]], como mecanismo principal).
- **Mark-and-sweep**: el recolector recorre periódicamente todos los objetos alcanzables desde las "raíces" del programa (variables globales, pila de llamadas) marcándolos como vivos, y luego libera todo lo no marcado.
- **Recolectores generacionales**: separan objetos "jóvenes" (se crean y mueren rápido, se revisan con frecuencia) de "viejos" (sobreviven más tiempo, se revisan con menos frecuencia) — usado por la JVM de Java y por Python como mecanismo complementario al conteo de referencias, para resolver referencias circulares que el conteo simple no puede detectar.

## Trade-offs
- **Ventaja**: elimina una clase entera de errores (fugas de memoria, doble liberación, uso de memoria ya liberada).
- **Costo**: el recolector consume tiempo de CPU y puede introducir pausas impredecibles en la ejecución — relevante en sistemas de tiempo real, donde a veces se prefiere el control manual explícito de C++.
- Java no tiene destructores propiamente dichos: el método `finalize()` cumple un rol similar pero sin garantía de cuándo (o si) se ejecutará, por lo que nunca debe ser la única vía para liberar recursos críticos (archivos abiertos, conexiones de red) — ver [[conceptos/constructores-destructores]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/constructores-destructores]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[entidades/python]]
