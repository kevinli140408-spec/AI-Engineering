---
titulo: "Introducción a la Programación con Python 3 (Marzal, Gracia, García)"
tipo: fuente
creado: 2026-07-01
actualizado: 2026-07-01
tags: [python, programacion, algoritmia, libro-de-texto, uji]
---

# Introducción a la Programación con Python 3 (Marzal, Gracia, García)

Libro de texto de Andrés Marzal Varó, Isabel Gracia Luengo y Pedro García Sevilla, *Introducción a la programación con Python 3* (Universitat Jaume I, colección Sapientia, 2014), 408 páginas — 8 capítulos. Es el material de la asignatura «Programación I» de los grados en Ingeniería Informática y Matemática Computacional de la UJI. A diferencia de [[fuentes/joyanes-aguilar-fundamentos-de-programacion]] (que enseña algoritmia en pseudocódigo con Python como uno de varios lenguajes de referencia), este libro enseña a programar **directamente en Python** desde el primer capítulo, con mucho mayor detalle de sintaxis, mecánica de memoria y particularidades reales del lenguaje. Ingesta completa: capítulo por capítulo.

## Cobertura
- [x] Cap. 1 — Introducción
- [x] Cap. 2 — Una calculadora avanzada
- [x] Cap. 3 — Programas
- [x] Cap. 4 — Estructuras de control
- [x] Cap. 5 — Tipos estructurados: secuencias
- [x] Cap. 6 — Funciones
- [x] Cap. 7 — Tipos estructurados: clases y diccionarios
- [x] Cap. 8 — Ficheros

## Capítulo 1 — Introducción
Cubre los fundamentos del computador (memoria, Unidad de Control, Unidad Aritmético-Lógica, CPU), la representación binaria de la información (bits, bytes, tabla ASCII, y las tres codificaciones de enteros con signo: signo-magnitud, complemento a uno y complemento a dos), la evolución de los lenguajes de programación (código de máquina → lenguaje ensamblador → lenguajes de alto nivel), la distinción entre compiladores e intérpretes (con la analogía de traductor de libros vs. intérprete simultáneo de conferencias), por qué el libro elige Python frente a Java, y el concepto formal de algoritmo (independiente del lenguaje, con la analogía de la receta de cocina para ilustrar sus 5 propiedades: entrada, salida, precisión, finitud y efectividad) junto a su origen histórico (Al-Khwarizmi, Euclides). Se solapa en gran parte con el Cap. 1 de [[fuentes/joyanes-aguilar-fundamentos-de-programacion]], por lo que la mayoría del contenido actualiza páginas existentes.

Páginas actualizadas: [[conceptos/representacion-de-la-informacion]], [[conceptos/lenguajes-de-programacion]], [[conceptos/algoritmo]], [[entidades/python]], [[entidades/guido-van-rossum]]. Página nueva: [[entidades/java]].

## Capítulo 2 — Una calculadora avanzada
Cubre el entorno interactivo de Python (REPL), los operadores aritméticos con su tabla completa de precedencia y asociatividad (11 niveles, con la particularidad de que `**` asocia por la derecha), árboles sintácticos para visualizar el orden de evaluación, la rareza de los comparadores encadenados en Python (`2 < 3 < 4` como conjunción implícita, a diferencia de C/Pascal), los tipos `int`/`float` (con el detalle de la codificación IEEE 754 de doble precisión y sus limitaciones de precisión) y `bool`, literales en base 2/8/16, variables y asignaciones (con el énfasis en que "una asignación no es una ecuación"), reglas de identificadores y palabras reservadas, el tipo cadena básico, funciones predefinidas (`abs`, `int`, `float`, `str`, `bin`/`oct`/`hex`, `round`, `ord`/`chr`), el sistema de módulos e importación (`math`, `sys`), y el método `format` de las cadenas.

Páginas actualizadas: [[conceptos/operadores-y-expresiones]], [[conceptos/variable-programacion]], [[conceptos/cadenas-de-caracteres]], [[conceptos/funciones-programacion]], [[conceptos/representacion-de-la-informacion]].

## Capítulo 3 — Programas
Cubre la distinción entre sesión interactiva y programa (script) en fichero `.py`, configuración de un IDE (Eclipse/Pydev, tratado como procedimiento técnico, no como contenido conceptual), lectura de datos por teclado (`input`), la función `print` (incluido el parámetro `end`), convenciones de legibilidad (nombres descriptivos, separación en zonas de un programa) ilustradas con un ejemplo de contraste, comentarios con `#`, y una introducción a gráficos con el módulo `turtle` (gráficos de tortuga), incluyendo su origen histórico en el lenguaje educativo Logo.

Páginas actualizadas: [[conceptos/estilo-y-documentacion]]. Página nueva: [[conceptos/graficos-de-tortuga]].

## Capítulo 4 — Estructuras de control
Cubre la sentencia `if`/`elif`/`else` con trazas de ejecución detalladas, condicionales anidados, evaluación con cortocircuito de `and`/`or`, las leyes de De Morgan aplicadas a negaciones de condiciones compuestas, las sentencias `while` y `for...in` (con la función `range` y el llamado "error Obi-Wan"/off-by-one), `break` y bucles anidados, y el manejo de excepciones con `try`/`except` (incluida la distinción por tipo de excepción, p. ej. `ZeroDivisionError` vs. `ValueError`). Cierra con dos ejemplos gráficos extensos (un graficador de funciones y una simulación gravitacional con `turtle`), tratados como ejercicios aplicados sin contenido conceptual nuevo más allá de lo ya cubierto.

Páginas actualizadas: [[conceptos/estructura-condicional]], [[conceptos/estructura-iterativa]], [[conceptos/depuracion-y-pruebas]], [[conceptos/metodologia-de-la-programacion]].

## Capítulo 5 — Tipos estructurados: secuencias
Cubre en profundidad las cadenas (secuencias de escape, indexación, recorrido, el operador de corte/slicing, conversión cadena↔lista con `split`/`join`), y las listas: comparación (`==`) vs. identidad (`is`), mutabilidad/inmutabilidad y su representación en memoria (referencias compartidas), lectura de listas por teclado, ordenación con el método de la burbuja (didáctico, sin usar `sort()`/`sorted()`), y matrices como "listas de listas" — incluida la trampa clásica de aliasing al construirlas con el operador `*`. Cierra con "El juego de la vida" como ejemplo aplicado extenso (no volcado a página propia).

Páginas actualizadas: [[conceptos/cadenas-de-caracteres]], [[conceptos/listas-python]], [[conceptos/arrays-vectores-matrices]], [[conceptos/algoritmos-ordenamiento]]. Página nueva: [[conceptos/mutabilidad-y-referencias]].

## Capítulo 6 — Funciones
Cubre la definición y uso de funciones (con uno, varios o ningún parámetro), procedimientos (funciones sin retorno), funciones que devuelven varios valores mediante una lista, ámbito de variables locales/globales (incluida la palabra clave `global` y el error `UnboundLocalError`), el mecanismo interno de la pila de llamadas y paso de parámetros, un ejemplo extenso (juego de memoria), varios ejemplos numéricos (integración numérica, bisección, combinatoria), recursividad (factorial, número de bits, Fibonacci, algoritmo de Euclides formulado recursivamente, Torres de Hanoi, recursión indirecta, fractales de Von Koch con `turtle`), diseño de módulos propios, y documentación del código mediante comentarios de cabecera.

Páginas actualizadas: [[conceptos/funciones-programacion]], [[conceptos/recursividad]].

## Capítulo 7 — Tipos estructurados: clases y diccionarios
Cubre la motivación y sintaxis concreta de clases en Python (`class`, `__init__`, `self`, métodos, métodos especiales como `__str__`), el problema de referencias/aliasing aplicado a objetos propios (análogo al ya visto con listas), clases de uso común desarrolladas como ejercicio (`Fecha`, `Cola`/`Pila`, cola de prioridad, `Conjunto` — todas implementadas desde cero, aunque Python ya ofrece equivalentes nativos como `set` o `heapq`), un ejemplo completo de gestión de un videoclub, y diccionarios (creación, consulta, recorrido, borrado, patrón de valores acumulativos) con una aplicación de listín telefónico.

Páginas actualizadas: [[conceptos/programacion-orientada-a-objetos]], [[conceptos/mutabilidad-y-referencias]], [[conceptos/pilas-y-colas]], [[conceptos/listas-python]], [[conceptos/estructuras-registros]]. Páginas nuevas: [[conceptos/conjuntos-python]], [[conceptos/diccionarios-python]].

## Capítulo 8 — Ficheros
Cubre generalidades sobre sistemas de ficheros (rutas, montaje de unidades — procedimental, poco conceptual), el protocolo abrir→leer/escribir→cerrar en Python (`open`, modos `'r'`/`'w'`/`'a'`, `readline`/`read`/`readlines`, `write`, `close`), la razón técnica para cerrar siempre un fichero (buffers de E/S), el módulo `pickle` para serializar estructuras de datos completas, y una introducción ligera a ficheros con formato (HTML, CGI, LaTeX) como ejemplo de por qué los ficheros de texto son una abstracción potente — tratado como contexto cultural, sin contenido Python específico nuevo.

Páginas actualizadas: [[conceptos/archivos-ficheros]].

## Contraste con otras fuentes del wiki
A diferencia de [[fuentes/joyanes-aguilar-fundamentos-de-programacion]] (pseudocódigo UPSAM, multilenguaje, énfasis en estructuras de datos avanzadas — árboles, grafos, TAD/UML) y de las fuentes cortas del curso UADE (`*-mm`, más introductorias), este libro es una inmersión profunda y exclusiva en Python: cubre con detalle la mecánica de memoria/referencias del lenguaje (mutabilidad, `is` vs. `==`), particularidades reales del intérprete (excepciones concretas, `IEEE 754`, comparadores encadenados) y construye desde cero varias estructuras de datos (`Conjunto`, `ColaPrioridad`) que Python ya ofrece nativas — con valor pedagógico explícito, no como recomendación de uso real.

## Referencias
- [[conceptos/algoritmo]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/operadores-y-expresiones]]
- [[conceptos/variable-programacion]]
- [[conceptos/cadenas-de-caracteres]]
- [[conceptos/funciones-programacion]]
- [[conceptos/estilo-y-documentacion]]
- [[conceptos/graficos-de-tortuga]]
- [[conceptos/estructura-condicional]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/listas-python]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/mutabilidad-y-referencias]]
- [[conceptos/recursividad]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/pilas-y-colas]]
- [[conceptos/estructuras-registros]]
- [[conceptos/conjuntos-python]]
- [[conceptos/diccionarios-python]]
- [[conceptos/archivos-ficheros]]
- [[entidades/python]]
- [[entidades/guido-van-rossum]]
- [[entidades/java]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
