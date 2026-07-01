---
titulo: "Lenguaje Algorítmico UPSAM 2.0 (referencia formal)"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [pseudocodigo, upsam, referencia, sintaxis]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Lenguaje Algorítmico UPSAM 2.0 (referencia formal)

Especificación formal del pseudocódigo en español usado en todo el libro (desarrollado en la Universidad Pontificia de Salamanca, de ahí "UPSAM"). Las páginas conceptuales del wiki ya explican el *significado* de cada construcción; esta página funciona como **hoja de referencia sintáctica** consolidada — ver [[conceptos/algoritmo]] para la estructura general `algoritmo...inicio...fin`.

## Elementos léxicos
- **Identificadores**: alfabéticos + dígitos + `_`, sensibles a mayúsculas, máx. recomendado 50 caracteres.
- **Comentarios**: `//` (una línea) o `{ }` (multilínea).
- **Tipos estándar**: `entero`, `real`, `lógico`, `carácter`, `cadena` (longitud variable por defecto, tratada como array de caracteres).

## Operadores y prioridad
Aritméticos (`+ - * / div mod **`), relacionales (`= < > <= >= <>`), lógicos (`no y o`), de cadena (`+ &`). Prioridad básica de mayor a menor: paréntesis/corchetes → unarios → multiplicativos/exponenciación → aditivos → de cadena → de relación. El libro también incluye una tabla de "prioridad avanzada" alineada a C++/Java/C# (con `++`, `--`, bit a bit, `?:`, asignación compuesta) — ver [[conceptos/operadores-y-expresiones]] para su desarrollo conceptual; el Apéndice B del libro repite esta misma tabla limitada a C/C++/Java sin agregar nada nuevo.

## Estructura de un programa y tipos estructurados
```
algoritmo <nombre>
[const ...] [tipos ...] [var ...]
inicio
  ...
fin
```
- **Array**: `array[<dimensión>...] de <tipo> : <nombre_tipo>` — ver [[conceptos/arrays-vectores-matrices]].
- **Registro**: `registro : <nombre> ... fin_registro`, acceso con `.` — ver [[conceptos/estructuras-registros]].
- **Archivos**: `archivo_s`/`archivo_d de <tipo> : <nombre>`, con `abrir`/`cerrar`/`leer`/`escribir`, `fda`/`fdl` (fin de archivo/línea), `lda` (tamaño) — ver [[conceptos/archivos-ficheros]].
- **Punteros**: `puntero_a <tipo> : <nombre>`, `reservar`/`liberar`, indirección con `↑` — ver [[conceptos/listas-enlazadas]].

## Biblioteca estándar de funciones
Aritméticas (`abs`, `raiz2`, `trunc`, `sen`, `cos`, `exp`, `ln`, `log10`, `aleatorio`), de cadena (`longitud`, `posición`, `subcadena`), de conversión (`código`/`carácter`, `valor`/`cadena`), `tamaño_de`. E/S básica: `leer`/`escribir`.

## Estructuras de control (sintaxis exacta)
- Selectiva: `si...entonces...[si_no...]fin_si`; múltiple: `según_sea...hacer...[si_no...]fin_según`.
- Repetitivas: `mientras...hacer...fin_mientras`; `repetir...hasta_que`; `desde <var> <inicio> hasta <fin> [incremento|decremento <n>] hacer...fin_desde` — ver [[conceptos/estructura-condicional]] y [[conceptos/estructura-iterativa]].

## Programación modular
`procedimiento`/`fin_procedimiento` y `<tipo>:función.../devolver(...)/fin_función`. Parámetros: `E` (por valor) o `E/S` (por referencia) — ver [[conceptos/funciones-programacion]].

## Programación orientada a objetos (sintaxis explícita del pseudocódigo)
- `clase <nombre>...fin_clase`; instanciación con `nuevo <constructor>(...)`; acceso a miembros con `.`.
- Constructor homónimo a la clase; **no existen destructores explícitos** — el pseudocódigo asume recolección de basura automática (a diferencia de C++, donde sí aplica, ver [[conceptos/constructores-destructores]]).
- Visibilidad: atributos **privados por defecto**, métodos **públicos por defecto**; modificadores `privado`/`público`/`protegido`, `estático`, `const` — ver [[conceptos/uml-diagrama-de-clases]].
- Herencia: `clase <derivada> hereda_de [<especificador_acceso>] <superclase>`, acceso a la superclase con `super`, clases/métodos abstractos con la palabra `abstracta` — ver [[conceptos/herencia]] y [[conceptos/clases-abstractas]].
- La ligadura de métodos es siempre **dinámica** (en tiempo de ejecución), habilitando el polimorfismo.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/algoritmo]]
- [[conceptos/operadores-y-expresiones]]
- [[conceptos/estructura-condicional]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/funciones-programacion]]
- [[conceptos/arrays-vectores-matrices]]
- [[conceptos/estructuras-registros]]
- [[conceptos/archivos-ficheros]]
- [[conceptos/listas-enlazadas]]
- [[conceptos/uml-diagrama-de-clases]]
- [[conceptos/constructores-destructores]]
- [[conceptos/herencia]]
- [[conceptos/clases-abstractas]]
