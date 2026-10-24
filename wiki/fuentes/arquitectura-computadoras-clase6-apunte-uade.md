---
titulo: "Arquitectura de Computadoras — Clase 6: Apunte organizado con erratas (UADE)"
tipo: fuente
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, compuertas-logicas, sumadores, alu, erratas, tp, apunte]
---

# Clase 6: Apunte organizado con erratas (UADE)

Versión reorganizada (10 páginas) de las notas de la Clase 6 de [[entidades/uade]]. El contenido de fondo (álgebra de Boole, compuertas, circuitos combinacionales y secuenciales, ALU de 1 bit, contexto geopolítico de semiconductores) ya está en [[fuentes/arquitectura-computadoras-clase6-notas-uade]], [[fuentes/arquitectura-computadoras-clase6-uade]], [[conceptos/compuertas-logicas]] y [[conceptos/alu-de-1-bit]]. Aquí solo se registran los aportes nuevos.

## Erratas corregidas

| Tema | Apunte original | Valor correcto |
|---|---|---|
| Fórmula del XNOR | `(¬A·B) + (A·¬B)` | Esa es la del **XOR**. **XNOR = (A·B) + (¬A·¬B)**. Ambas son suma de productos |
| Pac-Man | "usa complemento a 2", límite 255 | Contador **sin signo de 8 bits** (en Ca2 de 8 bits el máximo sería 127) |
| Acarreo final de la cadena de sumadores | lo llamaba "overflow" | En números sin signo es el **flag C**; el overflow V (Ca2) se detecta con la regla de signos |
| Agenda | "Compuertas de Google" | Error de transcripción de "compuertas lógicas" |
| Circuito de 2 NOT + 2 AND + 1 OR | "equivale a un XNOR", con tabla inconsistente | La tabla no permite verificarlo; `(¬A·B)+(A·¬B)` es un XOR. Vale el **método** (columnas intermedias y comparar con las tablas conocidas) |
| "Lectura", "BCCs", "ejercicios sobre el cargador" | temas del parcial | Términos ininteligibles; **confirmar con el docente o la grabación** |
| Mapeo F0/F1 de la ALU de 1 bit | tabla con "..." | El mapeo mostrado (abajo) es el típico del diseño clásico, no un dato de la clase |

**Posible tensión con el wiki**: [[conceptos/compuertas-logicas]] cita el ejemplo "~20 transistores equivalen a una XNOR de 4-5". Según este apunte la tabla de ese circuito era inconsistente, así que la equivalencia con XNOR no está verificada; la idea general (simplificar con álgebra de Boole reduce transistores) no cambia.

## Material nuevo para estudiar

### Sumador completo (full adder)

| A | B | Cin | Suma | Cout |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

**Suma = A ⊕ B ⊕ Cin** · **Cout = A·B + Cin·(A ⊕ B)** (Cout = 1 cuando al menos dos entradas valen 1). Suma y Cout dan en conjunto el total en decimal (0 a 3).

### Circuito combinacional resuelto

`U = NOT A; V = NOT B; W = B AND C; X = NOT (V OR W)`. Con 3 entradas hay 2³ = 8 filas (las primeras 4 con A=0). Resultado: **X = 1 solo cuando B=1 y C=0**; A no interviene. Método: una variable intermedia por compuerta y una columna por variable; no calcular de memoria.

### Otros puntos

- **XOR de más de dos entradas = paridad**: la salida es 1 si la cantidad de entradas en 1 es impar.
- **ALU de 8 bits** (interfaz en "V"): entradas A (8 bits), B (8 bits) y opcode (4 bits); salidas resultado (8 bits) y flags. Ejemplo: `1000` = ADD, `1100` = SUBTRACT. Z sirve para comparar igualdad (A−B=0) y N para comparar magnitud (A<B si A−B es negativo).
- **Mapeo F0/F1** (ALU de 1 bit, 2 señales → 2² = 4 combinaciones): 00 AND, 01 OR, 10 NOT B, 11 suma.
- **Ejemplo de enable**: con A=1, B=0, Cin=0 y F0=F1=1 se habilita la suma → resultado 1, Cout 0. Si el multiplexor apuntara a una unidad inactiva, el resultado sería 0 sin importar A y B.
- **Multiplicación**: sin circuito dedicado se hace por sumas sucesivas (12×5 = 5 pasadas por el sumador); controles remotos y microondas lo hacen así.
- **Lógica ≠ aritmética**: en una operación lógica no hay acarreo, cada bit es independiente.

## Logística del TP y del parcial

- **Escrito**: carátula e índice; todo el material (trabajo, presentaciones, videos) se sube a Teams para revisión previa.
- **Exposición**: ~5 minutos (presentación o video) y debate. El apunte dice 5 min, mientras que la Clase 5 mencionaba mini-avances de 2 min ([[fuentes/arquitectura-computadoras-clase5-apunte-uade]]); son instancias distintas.
- **Debate**: no se trata de mostrar quién sabe más, sino de defender la tecnología propia y señalar las debilidades de la otra. Alcanzan intervenciones de 30 a 40 segundos por integrante; las preguntas salen de los trabajos entregados y corregidos.
- **Orden**: sorteo al inicio de la clase siguiente; si el integrante que debe pasar no llegó, el grupo no presenta. El desarrollo es grupal y la **defensa individual**.
- **Parcial**: no habrá repaso intensivo. Temas teóricos mencionados: instrucciones, interrupciones y Von Neumann vs. Harvard ([[conceptos/arquitectura-harvard]]). Se sugiere analizar las transcripciones de las clases con IA para detectar el tipo de ejercicios.
- **Práctica sugerida**: armar de memoria las tablas de AND, OR, NOT, XOR, NAND, NOR y XNOR; completar el sumador completo; sumar 4 u 8 bits con acarreos; explicar decodificador, multiplexor y enable.

## Referencias
- Archivo original: `Clase_6_Apunte.pdf` (movido a `raw/assets/Arquitectura de Computadoras/apuntes/`)
