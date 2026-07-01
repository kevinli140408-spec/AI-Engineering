---
titulo: "Principios de Diseño de Software"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [diseno-de-software, abstraccion, modularidad, calidad-de-software, ingenieria-de-software]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Principios de Diseño de Software

Conjunto de objetivos que guían el diseño de sistemas de software de calidad, más allá de la resolución de un problema puntual — el marco en el que se apoyan la [[conceptos/metodologia-de-la-programacion|metodología de la programación]] y el [[conceptos/ciclo-de-vida-del-software|ciclo de vida del software]].

## Abstracción, procedimental y de datos
La **abstracción** es el proceso de excluir detalles no significativos para el problema; permite tratar cada parte de un sistema como una **caja negra** (se conoce *qué* hace, no *cómo*). Dos tipos:
- **Abstracción procedimental**: separa el propósito de un subprograma de su implementación — se puede usar conociendo solo su nombre y parámetros.
- **Abstracción de datos**: se centra en las operaciones sobre un dato (un [[conceptos/tipo-abstracto-de-dato|Tipo Abstracto de Dato]]) en vez de en cómo se almacena o implementa — p. ej. usar `string` en C++ sin conocer su representación interna.

Ambas conducen naturalmente a la **ocultación de la información**: los detalles internos de una caja negra quedan inaccesibles para el resto del sistema, y solo se exponen mediante una interfaz — base directa del encapsulamiento en [[conceptos/programacion-orientada-a-objetos|POO]].

## Modularidad mediante diseño descendente
El [[conceptos/metodologia-de-la-programacion|diseño descendente]] (refinamiento sucesivo) produce **módulos** — el criterio de calidad de un diseño modular se mide con dos propiedades:
- **Acoplamiento**: grado de interdependencia entre módulos — debe ser **débil** (interfaces claras y mínimas).
- **Cohesión**: qué tan relacionadas están las partes internas de un módulo — debe ser **fuerte** (cada módulo resuelve una única tarea bien definida).

La regla general: *módulos débilmente acoplados y fuertemente cohesionados*. Beneficios: construcción y depuración independientes (incluso por distintos programadores), mayor legibilidad, y eliminación de código redundante (una operación repetida se extrae a un subprograma).

## Modificabilidad
Un sistema es modificable si un cambio pequeño en los requisitos exige solo un cambio pequeño en el código — consecuencia directa de módulos débilmente acoplados. Se favorece con el uso extensivo de subprogramas y de **constantes con nombre** en vez de constantes literales (cambiar `NumeroDeItems` en un solo lugar en vez de en cada uso del valor).

## Otros criterios de calidad
- **Comprensibilidad y fiabilidad**: un sistema simple se comprende y mantiene más fácilmente que uno complejo.
- **Interfaces de usuario**: hacer eco de las entradas leídas, etiquetar claramente las salidas.
- **Programación segura contra fallos**: validar entradas y parámetros (con precondiciones/postcondiciones), dar mensajes de error claros en vez de códigos crípticos.
- **Facilidad de uso** y **eficiencia** (tiempo/espacio) — ver trade-off con legibilidad más abajo.

## Pautas para el diseño de algoritmos
No existe un algoritmo para diseñar algoritmos, pero el libro propone seis pautas: (1) formular una solución precisa del problema; (2) buscar si ya existe un algoritmo aplicable; (3) buscar técnicas estándar; (4) elegir una estructura de datos adecuada; (5) dividir el problema en subproblemas (diseño descendente); (6) si todo falla, reiniciar desde el paso 1.

## Las "-idades" de calidad del software
El resumen del capítulo cierra con una lista de propiedades deseables de todo producto de software: **eficiencia** (buen uso de recursos), **verificabilidad** (soporta pruebas y validación), **facilidad de uso**, **robustez** (funciona incluso ante situaciones anormales, vía diseño simple y descentralización), **compatibilidad** (se combina con otros productos), **transportabilidad/portabilidad** (se traslada a otra plataforma con pocos cambios — favorecida por usar versiones estándar del lenguaje: ANSI/IEEE/ISO Pascal, ANSI C++, o lenguajes ya estandarizados como Java/C#), **integridad** (protege sus componentes de accesos no autorizados), **corrección** (cumple exactamente su especificación) y **reutilización** (sus partes se reutilizan en nuevas aplicaciones).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/ciclo-de-vida-del-software]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/algoritmo]]
- [[conceptos/estilo-y-documentacion]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/tipo-abstracto-de-dato]]
