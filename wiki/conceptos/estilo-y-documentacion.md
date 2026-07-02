---
titulo: "Estilo de Programación y Documentación"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [estilo-de-programacion, documentacion, legibilidad, buenas-practicas]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
---

# Estilo de Programación y Documentación

Convenciones de escritura y documentación que hacen un programa legible y mantenible por personas distintas de quien lo escribió — complementan los [[conceptos/principios-diseno-software|principios de diseño de software]].

## Reglas de estilo de programación
1. **Modularizar** ampliamente el programa (uso extensivo de subprogramas).
2. **Evitar variables globales** en subprogramas — rompen el aislamiento de los módulos y provocan efectos laterales.
3. **Nombres significativos para identificadores**: sustantivos para datos (`Salario`), verbos para procedimientos (`LeerCaracter`), formas de "ser/estar" para funciones lógicas (`EsVacio`). Convención: identificadores propios en mayúsculas/minúsculas alternadas (`SalarioMes`), tipos definidos por el usuario en minúscula inicial, identificadores cortos (`i`, `j`, `k`) solo para variables locales muy acotadas (contadores de bucle).
4. **Definir constantes con nombre** (`constante Pi = 3.141592`) en vez de literales sueltos en el código.
5. **Evitar `goto`** — casi siempre viola el flujo de control ordenado (entrada única al módulo, salida única, condiciones de terminación claras) y dificulta verificar la corrección del programa.
6. **Uso adecuado de parámetros valor/variable**: parámetros valor cuando el subprograma no necesita devolver cambios (comunicación de un solo sentido); parámetros variable solo cuando el procedimiento debe devolver más de un valor.
7. **Funciones sin efectos laterales**: una función solo debe devolver un valor — no debe modificar variables globales ni usar parámetros variable; si se necesita eso, usar un procedimiento.
8. **Tratamiento de errores**: cada subprograma debe comprobar entradas/parámetros no válidos y decidir con claridad si resuelve el error él mismo o delega la decisión a quien lo llamó (p. ej. devolviendo un indicador lógico).
9. **Legibilidad**: buena elección de identificadores, sangrado (indentación) consistente de 3 a 5 espacios por nivel, alineación de palabras clave compuestas (`inicio`/`fin`), líneas en blanco que separen bloques lógicos.

## La documentación
Dos propósitos y audiencias distintas:
- **Documentación de usuario**: no técnica, explica cómo usar el software (también funciona como herramienta de marketing) — debe cubrir cómo arrancar el programa, archivos externos que usa, formato de mensajes de error, opciones de funcionamiento y ejemplos de salida.
- **Documentación del sistema (manual de mantenimiento)**: técnica, permite mantener el software durante todo su ciclo de vida — incluye especificaciones originales, diagramas de flujo de datos (DFD), diagramas entidad-relación (DER), diccionario de datos y diagramas de estructura.

La documentación del sistema se divide a su vez en:
- **Documentación interna**: contenida en el propio código como comentarios (cabecera del programa con autor/fecha/descripción, comentarios por módulo, comentarios en el cuerpo para partes complejas).
- **Documentación externa**: ajena al código fuente — especificación del programa, diagrama de estructura, formatos de datos y de pantallas, explicación de fórmulas complejas.

### Reglas de documentación
Un comentario de cabecera completo debe incluir: (1) descripción/propósito del programa; (2) autor y fecha; (3) descripción de entrada y salida; (4) cómo utilizar el programa; (5) hipótesis sobre los datos esperados; (6) descripción breve de algoritmos y estructuras de datos globales; (7) descripción de las variables importantes. Regla de oro: **documentar a medida que se progresa**, no como última etapa — y mantener siempre sincronizados comentario y código tras cualquier cambio.

## Un programa vs. una sesión interactiva
Un **programa** (o *script*) es el contenido de un fichero de texto (extensión `.py`) con una secuencia de sentencias que se ejecutan una tras otra de una sola vez, a diferencia de la sesión interactiva del intérprete, donde cada expresión se evalúa y muestra inmediatamente ([[fuentes/introduccion-a-la-programacion-con-python-3]]). Dentro de un fichero, mostrar un valor por pantalla requiere una llamada explícita a `print()` — a diferencia del modo interactivo, donde el resultado de cada expresión se imprime automáticamente. `print()` admite el parámetro `end=` para reemplazar el salto de línea por defecto (p. ej. `print(x, end=' ')`).

## Ejemplo ilustrativo de legibilidad (Python)
El libro contrasta dos programas equivalentes que calculan área y perímetro de un rectángulo: uno con variables de una sola letra reutilizadas para propósitos distintos (`h`, `v`, `z`) y sin separación entre lectura/cálculo/impresión, y otro con identificadores descriptivos (`altura`, `anchura`, `área`, `perímetro`), líneas en blanco que separan las tres zonas del programa (entrada → proceso → salida) y mensajes informativos en cada `input()`/`print()`. La lección: nombrar bien y estructurar en zonas claras cuesta poco esfuerzo extra y paga dividendos cada vez que el código se vuelve a leer.

## Comentarios en Python
Empiezan con `#` y se extienden hasta el final de la línea; el intérprete los ignora por completo. Usos recomendados: cabecera del programa (nombre, propósito, autor, fecha), inicio de cada "zona" del programa indicando qué hace, y anotaciones puntuales al final de una línea compleja.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/ciclo-de-vida-del-software]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/algoritmo]]
- [[conceptos/graficos-de-tortuga]]
