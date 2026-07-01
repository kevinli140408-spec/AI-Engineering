---
titulo: "Fundamentos de Programación (Joyanes Aguilar)"
tipo: fuente
creado: 2026-06-30
actualizado: 2026-07-01
tags: [programacion, algoritmia, estructuras-de-datos, libro-de-texto, uade]
---

# Fundamentos de Programación (Joyanes Aguilar)

Libro de texto de Luis Joyanes Aguilar, *Fundamentos de Programación: Algoritmos, Estructuras de Datos y Objetos* (McGraw-Hill), 802 páginas — 18 capítulos + 4 apéndices. Es bibliografía principal del curso [[analisis/estructura-curso-algoritmia-uade|Fundamentos de Informática / Algoritmia (UADE)]]. Ingesta en curso: se procesa **capítulo por capítulo** por su extensión.

## Cobertura
- [x] Cap. 1 — Introducción a las computadoras y los lenguajes de programación
- [x] Cap. 2 — Metodología de la programación y desarrollo de software
- [x] Cap. 3 — Estructura general de un programa
- [x] Cap. 4 — Flujo de control I: estructuras selectivas
- [x] Cap. 5 — Flujo de control II: estructuras repetitivas
- [x] Cap. 6 — Subprogramas (subalgoritmos): funciones
- [x] Cap. 7 — Estructuras de datos I (arrays y estructuras)
- [x] Cap. 8 — Las cadenas de caracteres
- [x] Cap. 9 — Archivos (ficheros)
- [x] Cap. 10 — Ordenación, búsqueda e intercalación
- [x] Cap. 11 — Ordenación, búsqueda y fusión externa (archivos)
- [x] Cap. 12 — Estructuras dinámicas lineales (pilas, colas, listas enlazadas)
- [x] Cap. 13 — Estructuras de datos no lineales (árboles y grafos)
- [x] Cap. 14 — Recursividad
- [x] Cap. 15 — Tipos abstractos de datos, objetos y UML 2.1
- [x] Cap. 16 — Diseño de clases y objetos en UML
- [x] Cap. 17 — Relaciones entre clases (delegación, asociación, agregación, herencia)
- [x] Cap. 18 — Resolución de problemas y desarrollo de software
- [x] Apéndices A-D (lenguaje algorítmico, prioridad de operadores, ASCII/Unicode, sintaxis C)

## Capítulo 1 — Introducción a las computadoras y los lenguajes de programación
Cubre organización física de una computadora (arquitectura Von Neumann, UCP, memoria), representación de la información (sistemas de numeración, ASCII/Unicode, codificación de enteros/reales/imágenes/sonido), dispositivos de almacenamiento y E/S, redes/Internet/Web 2.0, software (sistema vs. aplicación, sistemas operativos) y lenguajes de programación (generaciones, compiladores vs. intérpretes, paradigmas, breve historia 1954-2000).

Páginas generadas/actualizadas: [[conceptos/lenguajes-de-programacion]] (actualizada con generaciones y proceso de compilación), [[conceptos/paradigmas-de-programacion]] (nueva), [[conceptos/organizacion-de-computadoras]] (nueva), [[conceptos/representacion-de-la-informacion]] (nueva), [[conceptos/redes-y-web]] (nueva).

## Capítulo 2 — Metodología de la programación y desarrollo de software
Cubre las fases de resolución de problemas con computadora (análisis, diseño, codificación, compilación/ejecución, verificación/depuración, mantenimiento, documentación), diseño descendente y refinamiento sucesivo, programación modular, las limitaciones de la programación estructurada (datos locales/globales) como motivación de la POO, y una introducción profunda a la Programación Orientada a Objetos (abstracción, clases/objetos, encapsulamiento, herencia, polimorfismo) con notación UML básica. También formaliza convenciones de pseudocódigo en español y la tabla de símbolos ANSI de diagramas de flujo.

Páginas generadas/actualizadas: [[conceptos/metodologia-de-la-programacion]] (nueva), [[conceptos/programacion-orientada-a-objetos]] (nueva), [[conceptos/algoritmo]] (actualizada con convención de pseudocódigo y tipos de error).

## Capítulo 3 — Estructura general de un programa
Cubre el concepto de programa (caja negra entrada-proceso-salida), tipos de instrucciones (asignación, lectura, escritura, bifurcación), elementos básicos (palabras reservadas, identificadores, constantes, variables), tipos de datos primitivos (entero, real, lógico, carácter/cadena) con sus rangos, expresiones y operadores (aritméticos, relacionales, lógicos) con tablas de precedencia comparando Pascal vs. C/C++/Java/C#, funciones internas, la operación de asignación (simple, múltiple, conversión de tipo), entrada/salida, y la estructura formal de un algoritmo en pseudocódigo (cabecera + `var`/`const` + `inicio...fin`) con convenciones de comentarios por lenguaje. Incluye ~20 ejercicios resueltos (intercambio de variables, factorial, ecuación cuadrática, mayor de tres números, etc.) de carácter pedagógico, no volcados a páginas propias.

Páginas generadas/actualizadas: [[conceptos/operadores-y-expresiones]] (nueva), [[conceptos/variable-programacion]] (actualizada con equivalencia a pseudocódigo algorítmico), [[conceptos/algoritmo]] (actualizada con estructura formal y convención de comentarios).

## Capítulo 4 — Flujo de control I: estructuras selectivas
Cubre el flujo de control y la estructura secuencial, las estructuras selectivas simple (`si-entonces`), doble (`si-entonces-si_no`) y múltiple (`según_sea`/`switch`, con varios modelos de sintaxis), el anidamiento de estructuras `si` ("en escalera"), y la sentencia `ir_a` (`goto`) — su mecánica, su mala fama histórica (crítica de Dijkstra) y por qué se evita en la programación estructurada moderna.

Página actualizada (sin páginas nuevas, por mapear casi 1:1 con contenido ya existente): [[conceptos/estructura-condicional]].

## Capítulo 5 — Flujo de control II: estructuras repetitivas
Cubre las cuatro estructuras repetitivas formales: `mientras` (pretest), `hacer-mientras`/do-while (posttest, continúa si verdadera), `repetir-hasta_que` (posttest, continúa si falsa) y `desde`/`para` (conteo fijo, equivalente a `for`). Detalla los 4 métodos de terminación de bucles controlados por datos (preguntar antes, lista con tamaño conocido, valor centinela, agotamiento de entrada), las sentencias de salto `interrumpir`(break)/`continuar`(continue), el diseño y anidamiento de bucles, y una extensa batería de ejercicios resueltos (factorial, sumas, máximo/mínimo de una serie, tablas de multiplicar con bucles anidados, detección de centinela).

Página actualizada (sin páginas nuevas, mapea sobre contenido ya existente): [[conceptos/estructura-iterativa]] — se agregó la tabla comparativa de las 4 estructuras, los métodos de terminación y la nota de contraste sobre `break`/`continue` vs. la restricción pedagógica del curso UADE.

## Capítulo 6 — Subprogramas (subalgoritmos): funciones
Cubre la distinción formal entre **función** (devuelve un único valor con `devolver`) y **procedimiento** (`llamar_a`, devuelve 0, 1 o varios resultados vía parámetros); ámbito de variables locales/globales y efectos laterales; los métodos de paso de parámetros (por valor, por referencia, por nombre, por resultado) con ejemplos comparativos detallados; funciones/procedimientos como parámetros de otros subprogramas; recursividad (factorial y Fibonacci recursivos, condición de terminación, trade-off recursión vs. iteración); sintaxis de funciones en C/C++/Java/C# (prototipos, paso por valor vs. por referencia en Java, sobrecarga de funciones en C++/Java).

Páginas actualizadas/generadas: [[conceptos/funciones-programacion]] (actualizada con función vs. procedimiento, ámbito, paso de parámetros, sobrecarga), [[conceptos/recursividad]] (nueva — se ampliará en el Cap. 14, dedicado enteramente a este tema).

## Capítulo 7 — Estructuras de datos I (arrays y estructuras)
Cubre la clasificación de tipos de datos (simples vs. estructurados, estáticos vs. dinámicos), arrays unidimensionales (vectores: notación, límites, rango, operaciones de asignación/lectura/escritura/recorrido/inserción/borrado con desplazamiento manual de elementos), arrays bidimensionales (matrices, notación `M[fila,columna]`) y multidimensionales, almacenamiento de arrays en memoria (fórmula de dirección, orden por filas vs. por columnas — C/Pascal/COBOL vs. FORTRAN), estructuras/registros (tipo heterogéneo, anidamiento de estructuras), arrays de estructuras (tablas de registros), uniones (campos que comparten memoria) y enumeraciones (`enum`). Incluye 12 actividades de programación resueltas (tablas, matrices, búsqueda con bandera, cuadrado mágico, multiplicación de matrices, etc.) y 28 ejercicios propuestos.

Páginas generadas: [[conceptos/arrays-vectores-matrices]] (nueva — vectores, matrices, almacenamiento en memoria), [[conceptos/estructuras-registros]] (nueva — estructuras/registros, uniones, enumeraciones). Página actualizada: [[conceptos/listas-python]] (se agregó sección de contraste con arrays estáticos).

## Capítulo 8 — Las cadenas de caracteres
Cubre el juego de caracteres (ASCII básico/ampliado, EBCDIC, Unicode, secuencias de escape), el concepto de cadena/subcadena, datos tipo carácter (constantes, variables estáticas/semiestáticas/dinámicas, representación en memoria: longitud fija, longitud variable con máximo, longitud indefinida), las operaciones formales con cadenas (`longitud`, comparación basada en código ASCII, concatenación `&`, `subcadena`, búsqueda `indice`/`posicion`) y otras funciones (`insertar`, `borrar`, `cambiar`, conversión `valor`/`cad`, `código`/`car`), con sus algoritmos de implementación manual cuando el lenguaje no las provee nativamente. Incluye 9 actividades resueltas (eliminar blancos, contar vocales/letras, cambio de base) y 11 ejercicios propuestos.

Página actualizada (sin páginas nuevas, mapea sobre contenido ya existente): [[conceptos/cadenas-de-caracteres]] — se agregó tabla comparativa pseudocódigo↔Python de las operaciones de cadena y una nota sobre representación interna.

## Capítulo 9 — Archivos (ficheros)
Cubre la jerarquía de datos (bit→carácter→campo→registro→archivo→base de datos), terminología (clave, registro físico/lógico, factor de bloqueo, soportes secuenciales/direccionables), las tres organizaciones de archivos (secuencial, directa/aleatoria con función hash y tratamiento de colisiones, secuencial indexada con área de índice/datos/desbordamiento), operaciones de gestión (`crear`/`abrir`/`cerrar`/`leer`/`escribir`/`borrar`, altas/bajas/modificaciones lógicas y físicas), streams en C++/Java, y archivos de texto vs. binarios. Capítulo enteramente nuevo respecto al wiki existente — el curso de Python (UADE) no había cubierto E/S de archivos hasta este punto. Incluye 6 actividades resueltas y 8 ejercicios propuestos, todos variaciones del mismo patrón algorítmico (abrir→mientras no fda→leer/escribir→cerrar).

Páginas generadas: [[conceptos/archivos-ficheros]] (nueva — jerarquía de datos, organización de archivos, operaciones, streams vs. Python `open()`), [[conceptos/algoritmos-archivos]] (nueva — algoritmos de creación/consulta/actualización, transformación de clave/hash, colisiones, indexación).

## Capítulo 10 — Ordenación, búsqueda e intercalación
Cubre ordenación interna de vectores (intercambio/burbuja con sus 3 variantes, inserción directa y binaria con análisis del número de comparaciones, Shell, quicksort con partición y pivote), búsqueda (secuencial con análisis de comparaciones, binaria con análisis logarítmico, y por transformación de claves/hashing con los métodos de truncamiento/plegamiento/módulo/mitad del cuadrado y tratamiento de colisiones), e intercalación de dos vectores ordenados. Incluye 3 actividades resueltas y ejercicios propuestos.

Páginas actualizadas (mapean sobre contenido ya existente): [[conceptos/algoritmos-ordenamiento]] (se agregó Shell y quicksort), [[conceptos/algoritmos-busqueda]] (se agregó análisis de comparaciones y búsqueda por hashing). Página nueva: [[conceptos/intercalacion]] (merge de vectores ordenados).

## Capítulo 11 — Ordenación, búsqueda y fusión externa (archivos)
Generaliza al contexto de archivos (datos que no caben en memoria central) los conceptos de ordenamiento e intercalación ya vistos en el Cap. 10: archivos ordenados por clave primaria/secundarias jerárquicas, fusión de archivos secuenciales mediante el concepto de "ventana" (registro actual visible de cada archivo, ya que no hay acceso aleatorio en cinta/disco secuencial), cuatro métodos de partición de archivos (clasificación interna por bloques, por contenido de un campo, selección por sustitución aprovechando orden parcial preexistente, por secuencias alternadas) y los algoritmos de clasificación externa propiamente dichos (mezcla directa duplicando longitud de secuencia en cada pasada, mezcla natural aprovechando tramos ya ordenados, mezcla de secuencias equilibradas con 4 archivos de trabajo). Capítulo más corto que los anteriores (24 páginas); mapea como extensión directa de [[conceptos/intercalacion]] y [[conceptos/algoritmos-archivos]] al caso de archivos grandes. Incluye 6 actividades resueltas y 8 ejercicios propuestos.

Página generada: [[conceptos/ordenacion-externa]] (nueva — partición y fusión de archivos, mezcla directa/natural/equilibrada). Páginas actualizadas con enlace cruzado: [[conceptos/intercalacion]], [[conceptos/algoritmos-archivos]].

## Capítulo 12 — Estructuras dinámicas lineales (pilas, colas y listas enlazadas)
Capítulo enteramente nuevo respecto al wiki existente — el curso de Python (UADE) no había cubierto punteros, nodos ni estructuras enlazadas a este nivel. Cubre la distinción estructuras estáticas vs. dinámicas, punteros (variable cuyo valor es una dirección), listas enlazadas simples (inserción/borrado/recorrido por puntero, sin desplazamiento de elementos), su implementación alternativa con arrays paralelos (lista de vacíos) cuando el lenguaje no soporta punteros, listas circulares (último nodo apunta al primero) y listas doblemente enlazadas (punteros ANT/SIG, recorrido bidireccional). Cubre también pilas (stack, LIFO, aplicación a llamadas a subprogramas y recursividad) y colas (queue, FIFO, con la solución de array circular para aprovechar memoria) y su variante doble cola (bicola). Incluye 4 actividades resueltas (lista enlazada de ventas con array, copiar pila, borrar n-ésimo elemento de pila, verificar palíndromo con pila+cola) y 10 ejercicios propuestos (entre ellos, función de Ackermann con pilas).

Páginas generadas: [[conceptos/listas-enlazadas]] (nueva — punteros, listas simple/circular/doblemente enlazada), [[conceptos/pilas-y-colas]] (nueva — pilas LIFO, colas FIFO, bicola, equivalente con `collections.deque`). Página actualizada con enlace cruzado: [[conceptos/recursividad]] (mecanismo de pila de llamadas).

## Capítulo 13 — Estructuras de datos no lineales (árboles y grafos)
Capítulo enteramente nuevo respecto al wiki existente. Cubre árboles generales (definición recursiva, terminología: hoja, padre/hijo, nivel, altura, bosque), árboles binarios (máx. 2 hijos, conversión de árbol general a binario, representación con punteros/listas enlazadas/arrays), recorridos (pre-orden, in-orden, post-orden, todos recursivos), el árbol binario de búsqueda (ABB: generaliza la búsqueda binaria a estructura dinámica, inserción/eliminación con sus 3 casos, recorrido in-orden produce orden), y grafos (terminología: vértice/arista/camino/adyacencia, dirigidos vs. no dirigidos, ponderados, completos, conectados; representación con matriz de adyacencia o lista de adyacencia, mención de recorrido en profundidad/anchura). Incluye 5 actividades resueltas (deducir expresiones de árboles, insertar/contar nodos, contar hojas, comparar árboles) y 9 ejercicios propuestos.

Páginas generadas: [[conceptos/arboles]] (nueva — árbol general, árbol binario, recorridos, ABB), [[conceptos/grafos]] (nueva — terminología, matriz/lista de adyacencia).

## Capítulo 14 — Recursividad
Capítulo dedicado enteramente a profundizar el tema introducido brevemente en el Cap. 6. Cubre recursión directa vs. indirecta/mutua, las 3 condiciones formales de un algoritmo recursivo correcto (no recursión infinita, caso base correcto, composición correcta), la comparación detallada recursión-vs-iteración (trade-offs de tiempo/memoria vs. claridad), recursión infinita y sus 3 requisitos para terminación normal, y una serie de problemas clásicos resueltos recursivamente: Torres de Hanoi, búsqueda binaria recursiva, y las implementaciones recursivas de quicksort y mergesort (con su función auxiliar de mezcla). Incluye 7 ejercicios y 5 problemas propuestos.

Página generada: [[conceptos/torres-de-hanoi]] (nueva — problema clásico de recursión "divide y vencerás"). Página ampliada significativamente: [[conceptos/recursividad]] (recursión directa/indirecta, condiciones de corrección, problemas clásicos). Páginas actualizadas con enlace cruzado: [[conceptos/algoritmos-busqueda]] (búsqueda binaria recursiva), [[conceptos/algoritmos-ordenamiento]] (mergesort recursivo, enlace a Torres de Hanoi).

## Capítulo 15 — Tipos abstractos de datos, objetos y modelado con UML 2.1
Formaliza y profundiza la introducción a POO ya hecha en el Cap. 2. Cubre las limitaciones de la programación estructurada (acceso global a datos, mal modelado de entidades del mundo real) como motivación; el **Tipo Abstracto de Dato (TAD)** como concepto formal del que la **clase** es la materialización en POO; el proceso de modelado de objetos en 4 pasos (identificar objetos → agrupar en clases → identificar atributos/operaciones → identificar relaciones); estado/comportamiento/identidad de un objeto; un desarrollo mucho más profundo de las 5 propiedades fundamentales (abstracción, encapsulamiento, ocultación de datos, herencia, polimorfismo) con analogías extendidas (control remoto, lavadora, jerarquías animal/vehículo) y la noción de ligadura dinámica; y **UML** como lenguaje de modelado: definición formal (sintaxis/semántica/pragmática), las dos categorías de diagramas (estructurales y de comportamiento), su propósito (gestionar la complejidad del diseño), su historia completa (OMT/Booch/OOSE → "los tres amigos" en Rational → UML 1.0 en 1997 → estandarización OMG → UML 2.0 en 2004 → UML 2.1.1 en 2007) y una mención a MDA como dirección futura. Incluye también una tabla comparativa de terminología OO entre 7 lenguajes. Incluye 11 ejercicios propuestos (identificación y diseño de objetos/clases), no volcados a páginas propias.

Página ampliada significativamente: [[conceptos/programacion-orientada-a-objetos]] (TAD formal, identificación de objetos en 4 pasos, propiedades con analogías extendidas, ligadura dinámica). Página generada: [[conceptos/uml]] (nueva — definición, tipos de diagramas, historia, MDA).

## Capítulo 16 — Diseño de clases y objetos: representaciones gráficas en UML
Desarrolla en profundidad la notación gráfica de UML que el Cap. 15 había dejado anunciada. Cubre la **representación de objetos** (rectángulo con nombre subrayado, instancias con nombre/anónimas, atributos con sintaxis `nombre: tipo = valor_por_defecto`, instancias múltiples), la definición de Booch de objeto como estado+comportamiento+identidad, los 5 tipos de mensaje (constructores, destructores, selectores, modificadores, iteradores), responsabilidad y restricciones formalizables con OCL; la **representación de clases** (rectángulo de 3 compartimentos, convenciones de nombre, reglas de visibilidad `+`/`#`/`-` con su tabla de acceso, sintaxis de declaración de clase en pseudocódigo UPSAM equivalente a C++/Java/C#); la **declaración de objetos** (operador `nuevo`/`new`, operador punto, especificadores de acceso público/privado/protegido con su tabla completa de alcance); y la mecánica de **constructores** (mismo nombre que la clase, sin retorno, constructor por defecto, sobrecarga), **destructores** (único por clase, `~`/`destructor`, contraste C++ manual con `delete` vs. recolección de basura automática en Java/C# y el método `finalize()`), **implementación en C++** (archivos de cabecera `.h`, clases compuestas) y **recolección de basura**. Incluye comparaciones de código en pseudocódigo, C++, Java, C# y Turbo Pascal (EJEMPLO 16.3: clase `Fecha` con validación, en 4 lenguajes). 15 ejercicios propuestos, no volcados a páginas propias.

Páginas generadas: [[conceptos/uml-diagrama-de-clases]] (nueva — notación de objetos/clases, visibilidad, declaración, OCL), [[conceptos/constructores-destructores]] (nueva — constructores, destructores, recolección de basura, clases compuestas). Página actualizada con enlaces cruzados: [[conceptos/programacion-orientada-a-objetos]] (secciones de modelado UML y ciclo de vida del objeto), [[conceptos/uml]] (enlace al nuevo desarrollo del diagrama de clases).

## Capítulo 17 — Relaciones entre clases: delegaciones, asociaciones, agregaciones, herencia
Desarrolla en profundidad las relaciones entre clases que el Cap. 2 había introducido superficialmente. Cubre las **tres relaciones estructurales** [Booch 2006]: **dependencia** (la más débil, "usa-un", línea punteada), **asociación** (línea continua, con multiplicidad, restricciones `{ordered}`/`{or}`/`{xor}`, asociación cualificada, asociación reflexiva, clase de asociación, asociación ternaria) y **agregación**/**composición** ("todo-parte"/"tiene-un", rombo vacío vs. relleno). Luego profundiza la **generalización/especialización** (jerarquía es-un, propiedades transitiva/asimétrica/no-reflexiva), la **herencia simple vs. múltiple** (con el problema clásico de ambigüedad de nombres en C++ y su resolución con `::`), la sintaxis de declaración de clases derivadas (`hereda_de`), y la **tabla completa de accesibilidad** según tipo de herencia (pública/privada/protegida) cruzada con tipo de miembro. Cierra con **clases y operaciones abstractas** (clase sin instancias, operación solo con signatura, redefinición en subclases concretas) — la base conceptual del polimorfismo que se tratará más adelante. Incluye numerosos ejemplos gráficos (jerarquías de vehículos, animales, empleados) y 13 ejercicios propuestos, no volcados a páginas propias.

Páginas generadas: [[conceptos/relaciones-entre-clases]] (nueva — dependencia, asociación con todas sus variantes, agregación, composición), [[conceptos/herencia]] (nueva — generalización/especialización, herencia simple/múltiple, sintaxis, tabla de accesibilidad), [[conceptos/clases-abstractas]] (nueva — clase y operación abstracta, redefinición). Página actualizada con enlaces cruzados: [[conceptos/programacion-orientada-a-objetos]] (fila de Herencia y sección de identificación de objetos enlazadas a las páginas nuevas).

## Capítulo 18 — Resolución de problemas y desarrollo de software: Metodología de la programación
Último capítulo del cuerpo principal del libro; cambia de registro de algoritmia/estructuras de datos a **ingeniería del software**. Cubre la abstracción como herramienta de resolución de problemas (descomposición procedimental, diseño descendente, abstracción procedimental y de datos, ocultación de la información) y su culminación en el diseño orientado a objetos (DOO) frente al diseño descendente puro; el **ciclo de vida del software** formal — modelo en cascada tradicional (Análisis/Diseño/Implementación/Pruebas/Instalación/Mantenimiento, con comparación de nomenclatura Pressman vs. Sommerville), sus críticas, y el **Proceso Unificado** de Jacobson/Booch/Rumbaugh (incepción/elaboración/construcción/transición) apoyado en UML; las fases de análisis (documento de especificación de requisitos, con ejemplos de nómina y directorio telefónico de alumnos) y diseño (arquitectónico vs. detallado, precondiciones/postcondiciones, diseño descendente vs. DOO); pruebas e integración (verificación formal, reglas de Myers/Davis, principio de Pareto, pruebas de ruta básica/caja negra/caja blanca, niveles de prueba, pruebas beta); mantenimiento, obsolescencia y evolución del software; **principios de diseño de sistemas** (modularidad con acoplamiento/cohesión formalizados, abstracción y encapsulamiento, modificabilidad, interfaces de usuario, programación segura contra fallos); **estilo de programación** (12 reglas: nombres significativos, constantes con nombre, evitar `goto`, uso correcto de parámetros valor/variable, funciones sin efectos laterales, tratamiento de errores, legibilidad/sangrado); **documentación** (de usuario vs. de sistema/mantenimiento, interna vs. externa, reglas de comentario de cabecera); **depuración** (tipos de error, técnicas con breakpoints/watches/sentencias `escribir`); diseño de algoritmos (6 pautas); eficiencia (ejemplo de optimización de búsqueda secuencial) vs. legibilidad; y transportabilidad. Cierra con las "-idades" de calidad del software (corrección, robustez, extensibilidad, reutilización, compatibilidad, transportabilidad, integridad, verificabilidad, eficiencia). No incluye sección de ejercicios (a diferencia de los capítulos anteriores).

Páginas generadas: [[conceptos/ciclo-de-vida-del-software]] (nueva — modelo en cascada, Proceso Unificado, roles cliente/desarrollador/usuario, iteración/obsolescencia), [[conceptos/principios-diseno-software]] (nueva — abstracción/ocultación, modularidad con acoplamiento/cohesión, modificabilidad, pautas de diseño de algoritmos, las "-idades" de calidad), [[conceptos/estilo-y-documentacion]] (nueva — 12 reglas de estilo, documentación de usuario/sistema, reglas de comentario de cabecera), [[conceptos/depuracion-y-pruebas]] (nueva — tipos de error, técnicas de depuración, técnicas de prueba caja negra/blanca, verificación formal, el depurador). Páginas actualizadas con enlaces cruzados: [[conceptos/metodologia-de-la-programacion]] (nueva sección "De la programación individual a la ingeniería de software"), [[conceptos/algoritmo]] (enlace desde tipos de error hacia el desarrollo completo de depuración y pruebas).

## Apéndices A-D — Lenguaje algorítmico UPSAM 2.0, prioridad de operadores, ASCII/Unicode, sintaxis de C
Bloque final del libro, de naturaleza distinta a los 18 capítulos: son material de **referencia** (especificaciones formales y tablas), no desarrollo conceptual nuevo. **Apéndice A**: especificación formal completa del pseudocódigo UPSAM 2.0 usado en todo el libro — elementos léxicos, operadores y su prioridad, estructura de un programa, declaración de tipos estructurados (arrays, registros, archivos), biblioteca estándar de funciones, estructuras de control, programación modular y la sintaxis explícita de POO en pseudocódigo (clases, visibilidad por defecto, herencia, `super`, ligadura dinámica), cerrando con el listado completo de palabras y símbolos reservados. **Apéndice B**: tabla de prioridad de operadores para C/C++/Java — duplica textualmente la tabla "avanzada" ya incluida en el Apéndice A. **Apéndice C**: tablas de códigos ASCII (estándar, ampliado, códigos de teclado) y una introducción al consorcio Unicode — datos de referencia (lookup) sin contenido conceptual nuevo respecto al ya cubierto en el Cap. 1. **Apéndice D**: guía de sintaxis del lenguaje C — preprocesador (`#define`/macros, `#include`, compilación condicional), tipos de datos con tablas de tamaño/rango, operadores propios de C (bit a bit, incremento/decremento, ternario), sentencias de control con sintaxis de llaves, structs/uniones/campos de bits, punteros (incluidos punteros a punteros y a funciones) y E/S con formato (`printf`/`scanf`). Cierra el libro una bibliografía extensa (no ingerida — son solo referencias bibliográficas, sin contenido propio).

Páginas generadas: [[conceptos/lenguaje-algoritmico-upsam]] (nueva — hoja de referencia formal del pseudocódigo, consolidando y enlazando lo ya explicado en páginas de capítulos anteriores), [[conceptos/guia-sintaxis-c]] (nueva — preprocesador, macros, tipos/tamaños, punteros a funciones, campos de bits: lo específico de C no cubierto en otras páginas). Página actualizada: [[conceptos/representacion-de-la-informacion]] (nota sobre las tablas ASCII/Unicode completas del Apéndice C, sin volcarlas a página propia por ser datos de lookup).

## Referencias
- [[analisis/estructura-curso-algoritmia-uade]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/paradigmas-de-programacion]]
- [[conceptos/organizacion-de-computadoras]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/redes-y-web]]
- [[conceptos/metodologia-de-la-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/algoritmo]]
- [[conceptos/operadores-y-expresiones]]
- [[conceptos/variable-programacion]]
- [[conceptos/estructura-condicional]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/funciones-programacion]]
- [[conceptos/recursividad]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/estructuras-registros]]
- [[conceptos/listas-python]]
- [[conceptos/cadenas-de-caracteres]]
- [[conceptos/archivos-ficheros]]
- [[conceptos/algoritmos-archivos]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/intercalacion]]
- [[conceptos/ordenacion-externa]]
- [[conceptos/listas-enlazadas]]
- [[conceptos/pilas-y-colas]]
- [[conceptos/arboles]]
- [[conceptos/grafos]]
- [[conceptos/torres-de-hanoi]]
- [[conceptos/uml]]
- [[conceptos/uml-diagrama-de-clases]]
- [[conceptos/constructores-destructores]]
- [[conceptos/relaciones-entre-clases]]
- [[conceptos/herencia]]
- [[conceptos/clases-abstractas]]
- [[conceptos/ciclo-de-vida-del-software]]
- [[conceptos/principios-diseno-software]]
- [[conceptos/estilo-y-documentacion]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/lenguaje-algoritmico-upsam]]
- [[conceptos/guia-sintaxis-c]]
