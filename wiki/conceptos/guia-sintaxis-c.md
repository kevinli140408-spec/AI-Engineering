---
titulo: "Guía de Sintaxis del Lenguaje C"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [lenguaje-c, preprocesador, punteros, sintaxis]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Guía de Sintaxis del Lenguaje C

Referencia de elementos sintácticos propios de **C** que no quedan cubiertos por las páginas conceptuales generales del pseudocódigo — complementa [[conceptos/lenguaje-algoritmico-upsam]] con lo específico del lenguaje C (desarrollado en Bell Laboratories) para quien traduce algoritmos a código real.

## Estructura de un archivo fuente
Orden convencional: comentarios (`/* */`) → directivas de preprocesador → declaraciones globales de variables/funciones → definiciones (cuerpos) de funciones. Programa mínimo:
```c
#include <stdio.h>
int main() {
  printf("¡Hola mundo!");
  return 0;
}
```

## Tipos de datos y tamaños
C tiene enteros (`char`, `short`, `int`, `long`, con variantes `signed`/`unsigned`) y reales (`float`, `double`, `long double`), cada uno con rango dependiente de su tamaño en bytes (p. ej. `int` de 2 bytes: -32.768 a 32.767). No existe tipo lógico nativo: `0` es falso, cualquier valor distinto de cero es verdadero. `enum` declara listas ordenadas de constantes enteras (por defecto desde 0); `typedef` asigna un nombre nuevo a un tipo existente sin crear un tipo nuevo. Los cualificadores `const` (valor inmodificable) y `volatile` (valor que puede cambiar externamente, p. ej. un puerto de E/S) modifican una declaración.

## El preprocesador
Se ejecuta antes de la compilación; toda directiva comienza con `#`.
- **`#define`**: define constantes (`#define PI 3.141592`) o **macros** con parámetros (`#define cuadrado(x) ((x)*(x))`) — sustitución textual, no una función real.
- **`#include <archivo>`** busca en el directorio estándar de cabeceras; **`#include "archivo"`** busca en el directorio del proyecto.
- **Compilación condicional**: `#if`/`#elif`/`#else`/`#endif` (evalúan una expresión constante), `#ifdef`/`#ifndef` (evalúan si un identificador está definido) — útil para código multiplataforma o para evitar procesar dos veces un mismo header (*include guards*).
- Otras: `#undef` (quita una definición), `#error`, `#pragma`, `#line`. Identificadores predefinidos: `__LINE__`, `__FILE__`, `__DATE__`, `__TIME__`, `__STDC__`.

## Operadores propios de C
Más allá de los aritméticos/relacionales/lógicos ya vistos en [[conceptos/operadores-y-expresiones]]: incremento/decremento (`++`/`--`, prefijo o postfijo), manipulación de bits (`& | ^ << >> ~`), asignación compuesta (`+= -= *= ...`), operador serie (`,`), operador condicional ternario (`a ? b : c`), `sizeof`, y conversión de tipo explícita `(tipo)expresión`. Tiene 15 niveles de precedencia (más granulares que el pseudocódigo UPSAM).

## Sentencias de control
Sintaxis equivalente a las estructuras algorítmicas ya vistas ([[conceptos/estructura-condicional]], [[conceptos/estructura-iterativa]]) pero con llaves `{ }` en vez de `fin_si`/`fin_mientras`: `if`/`else`, `switch`/`case`/`break`/`default`, `while`, `do...while`, `for` (equivalente a `expr1; while(expr2){...; expr3;}`), además de `break`, `continue`, la sentencia nula (`;` sola) y `goto` con etiquetas.

## Funciones
`tipo_retorno nombre(tipo1 param1,...) {...; return expr;}`. ANSI C exige declarar un **prototipo** antes de usar una función. El tipo `void` indica ausencia de retorno o de parámetros. Errores típicos: falta de `return` en algún camino, ausencia de prototipo (se asume `int` por defecto), efectos laterales por modificar variables globales — coincide con las reglas de estilo ya vistas en [[conceptos/estilo-y-documentacion]].

## Estructuras de datos compuestas
- **Arrays**: siempre indexados desde `[0]`; `tipo nombre[n] = {...}`; multidimensionales con `[d1][d2]...`.
- **Cadenas**: arrays de `char` terminados en `'\0'` (carácter nulo); el preprocesador concatena literales de cadena adyacentes.
- **`struct`**: agrupa miembros heterogéneos, acceso con `.` — análogo a los registros de [[conceptos/estructuras-registros]], pero con `typedef struct` para evitar repetir la palabra `struct`.
- **`union`**: comparte una misma posición de memoria entre distintos tipos.
- **Campos de bits**: `unsigned campo : n;` dentro de un `struct`, para empaquetar enteros en menos bits de los que el compilador usaría normalmente.

## Punteros
`tipo *nombre` declara un puntero; `&` obtiene la dirección de una variable, `*` desreferencia. Un array y un puntero a su primer elemento son intercambiables (`lista[i]` ≡ `*(lista + i)`). Existen punteros a punteros (doble indirección, `char **`) y punteros a funciones (`int (*ptr)(void)`) — mecanismo mucho más explícito que los punteros abstractos de [[conceptos/listas-enlazadas]].

## Entrada/salida con formato
`printf`/`scanf` (de `stdio.h`) usan una cadena de control con identificadores de formato (`%d`, `%c`, `%s`, `%f`, `%x`, etc.) que deben coincidir en cantidad y tipo con la lista de argumentos.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/lenguaje-algoritmico-upsam]]
- [[conceptos/operadores-y-expresiones]]
- [[conceptos/estructura-condicional]]
- [[conceptos/estructura-iterativa]]
- [[conceptos/funciones-programacion]]
- [[conceptos/estructuras-registros]]
- [[conceptos/listas-enlazadas]]
- [[conceptos/estilo-y-documentacion]]
