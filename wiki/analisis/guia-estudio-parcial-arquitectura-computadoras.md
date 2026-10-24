---
titulo: "Guía de Estudio — Primer Parcial de Arquitectura de Computadoras (UADE)"
tipo: analisis
creado: 2026-09-16
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, uade, guia-de-estudio, parcial, representacion, alu]
fuentes: [arquitectura-computadoras-clase1-uade, arquitectura-computadoras-clase2-uade, arquitectura-computadoras-clase3-uade, arquitectura-computadoras-clase4-uade, arquitectura-computadoras-clase4-notas-uade, arquitectura-computadoras-clase4-apunte-uade, arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase5-notas-uade, arquitectura-computadoras-clase5-apunte-uade, arquitectura-computadoras-clase6-uade, arquitectura-computadoras-clase6-notas-uade, arquitectura-computadoras-clase6-apunte-uade, arquitectura-computadoras-clase7-apunte-uade]
---

# Guía de Estudio — Primer Parcial de Arquitectura de Computadoras

> **Alcance**: clases 1 a 6 (primer parcial). Documento autocontenido de estudio; consolida las páginas de conceptos de la wiki (excepción deliberada al límite de 500 palabras).
> **Dato clave**: se estima que **~3 de 5 puntos** del parcial salen de sistemas de numeración y representación ([[fuentes/arquitectura-computadoras-clase5-notas-uade]]). Priorizá los bloques 5 y 6, y **justificá siempre con flags** los ejercicios de rangos.
> **Actualización 2026-10-24**: se incorporaron los ejercicios y precisiones de los apuntes organizados de las Clases 4-6 (E15 a E19) y los consejos de la revisión del parcial de la Clase 7 (sección "Consejos para el examen"). Los valores que esos apuntes corrigen ya figuraban bien en esta guía.

---

## Bloque 1 — Electricidad básica ([[conceptos/electricidad-basica]])

### Magnitudes (analogía hidráulica)

| Magnitud | Definición | Unidad | Analogía |
|---|---|---|---|
| Tensión/Voltaje (V) | Diferencia de potencial que impulsa los electrones | Volt | Presión del agua |
| Corriente (I) | Flujo de electrones | Ampere | Caudal |
| Resistencia (R) | Oposición al paso de corriente | Ohm (Ω) | Estrechamiento de cañería |
| Potencia (P) | Energía por unidad de tiempo | Watt | — |

La tensión es siempre una **diferencia entre dos puntos**, nunca un valor absoluto.

### Leyes (memorizar)

- **Ohm**: `V = I × R` (despejes: `I = V/R`, `R = V/I`)
- **Potencia**: `P = V × I = I² × R`
- **Joule**: `Q = P × t = I² × R × t` — la energía disipada se transforma en calor

**Cortocircuito**: R → 0 hace que I → ∞ → sobrecalentamiento. Protecciones: llave térmica, disyuntor.

### CC vs. CA

- **CC** (continua): flujo unidireccional constante; es lo que consumen internamente todos los componentes electrónicos. Impulsor histórico: [[entidades/thomas-edison]].
- **CA** (alterna): cambia de sentido periódicamente (sinusoidal); estándar domiciliario (Argentina 220V/50Hz) por su eficiencia de transporte con transformadores. Impulsor: [[entidades/nikola-tesla]].

**Cadena eléctrica**: generación → transmisión en alta tensión (minimiza pérdidas) → subestación → distribución → consumo. El cargador hace el paso final: **rectifica CA → CC**.

**Cargadores**: el OUTPUT debe ser compatible en tensión, corriente máxima, tipo de corriente, conector y polaridad. Un cargador de menor potencia (60W para un equipo de 100W) carga más lento o no carga, pero **no daña** el equipo. Potencias USB: 2.0 = 2,5W · 3.0 = 4,5W · USB-C = 15W · USB-C PD = hasta 240W.

---

## Bloque 2 — Semiconductores y transistores ([[conceptos/semiconductores-y-transistores]])

- **Conductores** (cobre, oro, plata): poca resistencia. El oro se usa en contactos críticos porque no se oxida.
- **Aislantes** (plástico, madera): bloquean la corriente.
- **Semiconductores** (silicio, germanio): conducen o no según condiciones controladas (dopaje, campo eléctrico).

**Componentes pasivos**: el capacitor (aísla en CC, conduce en CA, almacena carga) y el inductor (comportamiento inverso) se usan para "aplanar" la señal al rectificar. La **válvula** fue el antecesor del transistor (ENIAC).

**Diodo**: conduce en un solo sentido (ánodo→cátodo, polarización directa). Un **puente de diodos** rectifica CA en CC pulsante — el corazón de todo cargador. El LED es un diodo que emite luz.

**Transistor** (Bell Labs, 1947): tres terminales (emisor, base, colector); interruptor/amplificador controlado eléctricamente. Circuito cerrado/abierto = 1/0 = **implementación física del bit** y del álgebra de Boole.

---

## Bloque 3 — Ley de Moore e historia ([[conceptos/ley-de-moore]], [[conceptos/historia-de-la-computacion]])

**Ley de Moore** ([[entidades/gordon-moore]], 1965): los transistores por chip se duplican ~cada 2 años. No es ley física sino tendencia industrial. Progresión: Intel 4004 (1971, 2.300) → Pentium (1993, 3,1M) → Core i7 (2010, 1.170M) → Apple M1 (2020, 16.000M) → NVIDIA B200 (2024, 208.000M).

**¿Sigue vigente?** Debate: NVIDIA dice que "murió"; Intel que sigue con matices. Límite físico: a ~2nm aparecen efectos cuánticos (**efecto túnel**). Estrategias de continuidad: **chiplets** (AMD Infinity Fabric) y **apilamiento 3D**.

**Hitos**: ENIAC (1946, válvulas, se programaba recableando) → Intel 4004 (1971, primer microprocesador) → Altair 8800 (1975, nace Microsoft) → Apple II (1977) → IBM PC (1981, Intel 8088 + MS-DOS = "Wintel") → Macintosh (1984).

**x86**: nombre de familia por los Intel 8086/286/386/486; al no ser patentable un número, AMD fabricó compatibles → competencia Intel-AMD. Evolución 16 → 32 → 64 bits (x64/AMD64). Hoy: **x86** (Intel/AMD, potencia) vs. **ARM** (Apple M1-M4, celulares; menor consumo).

---

## Bloque 4 — Von Neumann, CPU, buses e interrupciones

### Arquitectura de Von Neumann ([[conceptos/arquitectura-von-neumann]])

Propuesta de [[entidades/john-von-neumann]] (1945-46): **programa almacenado** — instrucciones y datos conviven codificados igual en la misma memoria. Antes (ENIAC) se "programaba" recableando.

**Los 5 componentes**: entrada · **UCP** (UC + ALU) · memoria principal · memoria secundaria · salida.

**Ciclo de instrucción (4 etapas)**: **Fetch → Decode → Execute → Write-back**, repetido indefinidamente, secuencial salvo saltos o interrupciones.

**Cuello de botella de Von Neumann**: programa y datos comparten un único bus → no se puede leer instrucción y dato a la vez.

### Harvard ([[conceptos/arquitectura-harvard]])

| Aspecto | Von Neumann | Harvard |
|---|---|---|
| Memoria | Única, compartida | Separada (instrucciones/datos) |
| Buses | Uno compartido | Dos independientes |
| Ejecución | Secuencial | Paralela (lee ambos a la vez) |
| Flexibilidad | Alta | Menor (tamaños fijos) |
| Costo | Menor | Hasta 10x mayor |

Harvard se usa en **sistemas embebidos** (ej. tomógrafo); las PCs siguen siendo Von Neumann.

### Componentes de la CPU ([[conceptos/componentes-de-la-cpu]])

- **UC**: busca, decodifica y dirige ("el cerebro dentro del cerebro").
- **ALU**: suma/resta (multiplicación = sumas sucesivas; división = restas sucesivas) y lógica (AND/OR); usa un **acumulador**.
- **Registros**: la memoria más rápida, dentro de la CPU. Generales (datos/direcciones) y específicos (**contador de programa**, **registro de estado/flags**).
- **Jerarquía de memoria**: `Registros > Caché (L1>L2>L3) > RAM > Almacenamiento`. La caché es solo transistores (la RAM combina transistores y capacitores) → más rápida y cara; mitiga el cuello de botella. **Cache hit** (dato ya está) vs. **cache miss** (ir a RAM); **dirty bit** = bloque modificado que debe escribirse a RAM antes de reemplazarse.
- **Reloj**: señal base BCLK (~100 MHz) multiplicada por **PLLs** por dominio. Más frecuencia = más calor (Joule). RAM DDR: transfiere en ambos flancos → MT/s = 2 × MHz.

### Buses ([[conceptos/buses-de-sistema]])

- **Direcciones**: unidireccional (CPU→memoria); con n bits se direccionan `2ⁿ` posiciones.
- **Datos**: bidireccional; transporta el contenido.
- **Control**: bidireccional; señales de coordinación (leer/escribir, habilitación, reloj).

**Lectura**: UC pone dirección en bus de direcciones → señal de habilitación por bus de control → la memoria pone el dato en el bus de datos → se guarda en un registro. **Escritura**: proceso inverso.

**Fórmula de memoria**: `Tamaño = 2ⁿ × Tamaño de Palabra` (n = bits del bus de direcciones; rango de direcciones `[0, 2ⁿ−1]`).

**Chipset**: Northbridge (RAM/gráficos) + Southbridge (periféricos lentos); hoy integrado en el procesador (PCH / I/O Die). Buses externos: PCIe, USB, SATA.

### Interrupciones ([[conceptos/interrupciones]])

Suspensión temporal del ciclo para atender un evento. **Tipos**: hardware (periférico, vía línea **IRQ**), software (instrucción `INT` para pedir servicio al SO), internas/excepciones (ej. división por cero). Se chequean **al final de cada ciclo** (entre write-back y el próximo fetch).

**Ciclo de interrupción**: evento → guardar contexto (flags + contador de programa) en la **pila** → consultar el **vector de interrupciones** → ejecutar la rutina de atención → recuperar contexto y retomar donde estaba. Evitan el "polling" y son la base de la multiprogramación.

---

## Bloque 5 — Sistemas de numeración ([[conceptos/sistemas-de-numeracion]])

**Posicional** (decimal, binario, octal, hex: el valor depende de la posición) vs. **no posicional** (romanos).

| Base | Nombre | Dígitos | Uso |
|---|---|---|---|
| 2 | Binario | 0,1 | Estados del transistor |
| 8 | Octal | 0-7 | Agrupa bits de a 3 |
| 10 | Decimal | 0-9 | Humano |
| 16 | Hexadecimal | 0-9,A-F | Agrupa bits de a 4 |

**Unidades**: bit → nibble (4 bits) → byte (8 bits) → palabra (tamaño nativo del registro: 16/32/64 bits).

### Conversiones (practicar hasta automatizar)

- **Binario → decimal**: sumar potencias de 2 donde hay 1. `1001₂ = 2³+2⁰ = 9`.
- **Decimal → binario**: restas sucesivas de potencias de 2, de mayor a menor. `73 = 64+8+1 = 2⁶+2³+2⁰ = 1001001₂`.
- **Hex ↔ binario**: cada dígito hex = exactamente 4 bits. `9F2₁₆ = 1001 1111 0010₂`. Al ir de binario a hex, rellenar con ceros a la izquierda hasta completar grupos de 4.
- **Octal ↔ binario**: grupos de 3 bits. **Octal ↔ hex**: no hay relación directa; pasar siempre por binario.
- **Hex → decimal**: conviene pasar por binario como paso intermedio.
- **Agrupar siempre de derecha a izquierda**; si el último grupo queda incompleto se rellena con ceros **a la izquierda** (no cambia el valor). Un cero a la derecha sí lo cambia (como `23` → `230` en decimal).
- **Escribir la base** de cada número (`85₁₀` ≠ `85₈`) y usar la base 2 como puente.
- **Decimal → binario**: primero calcular cuántos bits hacen falta (para 85, 6 bits cubren hasta 63 y no alcanzan; 7 sí).

**Direccionamiento**: con n bits hay `2ⁿ` direcciones (no confundir n con 2ⁿ); sumar **un** bit duplica la cantidad. Capacidad = direcciones × tamaño de palabra.

### Aritmética binaria

- **Suma**: `0+0=0` · `0+1=1` · `1+1=0 con acarreo 1` · `1+1+1=1 con acarreo 1`.
- **Resta**: si el minuendo es menor, se "pide prestado" a la posición siguiente.
- **Fracciones**: potencias negativas de 2 (`2⁻¹=0,5`, `2⁻²=0,25`, ...). Ej.: `20,8125₁₀ = 10100,1101₂`.

**KB vs. KiB**: comercial usa base 10 (KB=10³); el SO usa base 2 (KiB=2¹⁰=1024) → un disco de "1TB" muestra ~930GB.

---

## Bloque 6 — Representación de la información (⭐ el corazón del parcial)

### Los cinco sistemas de punto fijo ([[conceptos/representacion-numeros-enteros]])

| Sistema | Mecanismo | Rango (n bits) | 8 bits |
|---|---|---|---|
| **BSS** | Binario directo, sin signo | `[0, 2ⁿ−1]` | [0, 255] |
| **MyS** | MSB = signo, resto magnitud | `[−(2ⁿ⁻¹−1), +(2ⁿ⁻¹−1)]` | [−127, +127] |
| **Ca1** | Negativos: invertir todos los bits | `[−(2ⁿ⁻¹−1), +(2ⁿ⁻¹−1)]` | [−127, +127] |
| **Ca2** | Negativos: invertir bits **y sumar 1** | `[−2ⁿ⁻¹, +(2ⁿ⁻¹−1)]` | [−128, +127] |
| **Exceso** | guardado = real + bias (2ⁿ⁻¹) | `[−2ⁿ⁻¹, +(2ⁿ⁻¹−1)]` | [−128, +127] |

Puntos que toman en examen:
- MyS y Ca1 tienen **doble cero** (+0 y −0); Ca2 y exceso lo resuelven; Ca2 gana el valor extra **−128** (solo existe en Ca2).
- En los **positivos**, BSS, MyS, Ca1 y Ca2 **coinciden bit a bit**.
- **La ALU solo sabe sumar**: los complementos convierten la resta en suma (`10−5` → `10+(−5)`). Todos los operandos deben estar en el mismo sistema antes de operar.
- **Polisemia del binario**: la misma cadena vale distinto según el sistema con que se interprete.
- **Rango vs. representabilidad**: el rango lo fijan los bits y el sistema, no el número. Un valor fuera de rango no es "incorrecto": el sistema no tiene capacidad para contenerlo (ej. +130 entra en BSS pero no en los sistemas con signo de 8 bits).
- **Resultado aritmético vs. de procesador**: el aritmético muestra todos los bits (`1101+1100 = 11001`); el de la ALU se limita al ancho del registro (`1001`) y el bit sobrante queda en C=1. En un examen hay que interpretar cuál piden.
- **Con n bits el resultado se presenta siempre con los n bits**, aunque haya ceros a la izquierda.
- **Procedimiento para un negativo en Ca2**: módulo en binario → invertir (Ca1) → sumar 1. Ej. −3 en 4 bits: `0011 → 1100 → 1101`.
- **Exceso**: codificar = sumar bias; decodificar = restar bias. Es el formato del exponente en IEEE 754.
- **BCD**: cada dígito decimal por separado en 4 bits (25 → `0010 0101`); origen IBM/tarjetas perforadas. No es base 2 posicional.

### Flags Z, N, C, V ([[conceptos/flags-del-procesador]])

| Flag | Se pone en 1 cuando... |
|---|---|
| **Z** (Zero) | El resultado es todo ceros |
| **N** (Negative) | El MSB del resultado es 1 |
| **C** (Carry) | Hay acarreo saliente del MSB (o borrow en resta) |
| **V** (Overflow) | El resultado desborda el rango **en Ca2** |

**La clave conceptual**: la ALU suma bits sin saber qué representan. **C = fuera de rango si se lee como BSS; V = fuera de rango si se lee como Ca2.** Pueden darse ambos a la vez.

**Regla de signos para V** (rápida y segura): si `(+)+(+)=(−)` o `(−)+(−)=(+)` → V=1. Operandos de signos opuestos **nunca** desbordan.

**Overflows célebres**: Ariane 5 (float64→int16, 1996), problema del año 2038 (timestamp Unix de 32 bits), Pac-Man (nivel 256, contador de 8 bits).

### IEEE 754 ([[conceptos/punto-flotante-ieee754]])

| Formato | Total | Signo | Exponente | Mantisa | Bias |
|---|---|---|---|---|---|
| Float | 32 | 1 | 8 | 23 | 127 |
| Double | 64 | 1 | 11 | 52 | 1023 |

`Valor = ± 2^(E−127) × 1,M` — exponente en **exceso 127**; el `1,` de la mantisa está **implícito** (bit de precisión gratis). No todo decimal tiene representación exacta (`0.1` es aproximado).

### Códigos alfanuméricos

**ASCII** (7 bits) → **EASCII** (8 bits) → **Unicode** (code points) → **UTF-8** (1 a 4 bytes, retrocompatible con ASCII).

---

## Bloque 7 — Ciclo moderno: pipelining, CISC/RISC ([[conceptos/pipelining-y-superescalaridad]], [[conceptos/cisc-y-risc]])

### Pipelining (segmentación de cauce)

El ciclo se divide en etapas que se **superponen**: mientras una instrucción se ejecuta, la siguiente se decodifica y otra se capta. **Mejora el throughput, empeora la latencia individual** (por sincronización entre etapas).

**Conflictos (hazards)**: estructural (dos etapas piden el mismo recurso), dependencia de datos (una instrucción necesita el resultado de la anterior), control (los saltos invalidan lo captado).

**Mitigaciones modernas**: **prefetching** (cargar por anticipado en caché), **branch prediction** (adivinar el salto; si erra, descarta y paga penalización), **ejecución fuera de orden** (reordenar instrucciones independientes). Las instrucciones de **tamaño uniforme** (RISC) hacen predecibles las etapas.

**Superescalar**: múltiples cauces paralelos con sus propias unidades funcionales → varias instrucciones iniciadas por ciclo. **Multithread** (hilos por núcleo, los maneja el SO) y **multicore** (núcleos físicos).

### ISA, CISC vs. RISC

**ISA** = interfaz hardware-software: define instrucciones, tipos de datos, registros. Dominantes: **x86** y **ARM**.

| CISC | RISC |
|---|---|
| Más instrucciones | Menos instrucciones |
| Ciclos **variables** por instrucción | Ciclos **fijos** |
| Tamaño de instrucción **variable** | Tamaño **fijo** |
| Opera en memoria y registros | Solo en registros |
| Menos instrucciones por programa | Más instrucciones por programa |
| Carga en el **hardware** (+consumo/calor) | Carga en el **compilador/software** |

- **Regla 80/20**: ~80% de las operaciones son simples; RISC optimiza ese 80%.
- Ej.: `3+7` = 1 instrucción compleja en CISC vs. cargar-cargar-sumar-almacenar en RISC.
- **Límite térmico (~2014)** → convergencia: núcleos híbridos efficiency/performance (Apple M1).
- **Incompatibilidad de ISA**: un binario x86 no corre nativo en ARM (emulación = pérdida de rendimiento).
- **x86 vs x64**: x86 = 32 bits; x64 extiende a 64 bits, más RAM, retrocompatible. Ambas ISA usan **Ca2** para enteros e **IEEE 754** para flotantes; x86 es little endian, ARM configurable (little/big).

---

## Bloque 8 — Álgebra de Boole, compuertas y ALU ([[conceptos/compuertas-logicas]], [[conceptos/alu-de-1-bit]])

### Historia mínima

[[entidades/george-boole]] (1854): álgebra con variables 0/1 y operaciones OR (+), AND (·), NOT. [[entidades/claude-shannon]] (1938): la aplicó a circuitos — el puente lógica↔hardware.

### Las 7 compuertas (saber sus tablas de verdad)

| Compuerta | Salida = 1 cuando... |
|---|---|
| **OR** | Alguna entrada es 1 |
| **AND** | Todas las entradas son 1 |
| **NOT** | La entrada es 0 |
| **NOR** | Ninguna entrada es 1 |
| **NAND** | No todas son 1 |
| **XOR** | Cantidad **impar** de entradas en 1 (paridad) |
| **XNOR** | XOR negada: las entradas son iguales |

⚠️ No confundir las fórmulas (ambas suma de productos): **XOR = (¬A·B) + (A·¬B)** y **XNOR = (A·B) + (¬A·¬B)**.

**Lógica ≠ aritmética**: en las operaciones lógicas **no hay acarreo** (`1 OR 1 = 1`; en suma binaria `1+1 = 10`).

### Combinacional vs. secuencial

- **Combinacional**: salida depende solo de las entradas actuales; sin memoria.
- **Secuencial**: depende también del **estado anterior**, vía **realimentación** (la salida vuelve a la entrada) — base de flip-flops y registros. Ejemplo de clase: la luz de parada del colectivo queda encendida hasta que se abre la puerta.

**Equivalencia**: dos circuitos con la misma tabla de verdad son equivalentes → se simplifica para reducir transistores (AND = transistores en serie; OR = en paralelo). Chips reales: 7408 (4 AND), 7400 (4 NAND).

### De compuertas a ALU (escalera de abstracción)

1. **Semi-sumador (half adder)**: Suma = A **XOR** B · Acarreo = A **AND** B.
2. **Full adder**: agrega C_in; = **2 half adders + 1 OR** (combina los acarreos). Entradas A, B, C_in; salidas S, C_out. **S = A ⊕ B ⊕ C_in** · **C_out = A·B + C_in·(A ⊕ B)** (C_out = 1 cuando al menos dos entradas valen 1).
3. **Sumador de 8 bits**: 8 full adders encadenados (C_out → C_in del siguiente; el primero con C_in=0). **Ripple carry** (cascada, lento) vs. **carry look-ahead** (anticipa acarreos). El acarreo final alimenta el flag **C**.
4. **ALU de 1 bit**: full adder + AND + OR + NOT en paralelo sobre A y B; un **multiplexor** selecciona cuál salida sale, según el **opcode** decodificado (ej. `1000`=ADD, `1100`=SUBTRACT; el decodificador habilita una sola entrada con señales *enable*). Encadenando n celdas → ALU de n bits.

En una ALU de 8 bits no existe "noveno bit": el acarreo excedente va al registro de estado. Hito: el **Intel 4004 (1971)** integró la arquitectura completa en un chip.

---

## Ejercicios resueltos

### E1 — Ley de Ohm y potencia
**Un componente con R = 6Ω recibe 12V. ¿Corriente, potencia y calor en 10 minutos?**
- `I = V/R = 12/6 = 2A`
- `P = V×I = 12×2 = 24W` (verificación: `I²×R = 4×6 = 24W` ✓)
- `Q = P×t = 24 × 600s = 14.400 J`

### E2 — Decimal → binario (restas sucesivas)
**Convertir 73₁₀:** mayor potencia que entra: 64 → resto 9; entra 8 → resto 1; entra 1 → resto 0.
`73 = 2⁶+2³+2⁰ = `**`1001001₂`**

### E3 — Fracción decimal → binario
**Convertir 20,8125₁₀:** parte entera: `20 = 16+4 = 10100₂`. Parte fraccionaria: `0,8125 = 0,5+0,25+0,0625 = 2⁻¹+2⁻²+2⁻⁴ = 0,1101₂`.
Resultado: **`10100,1101₂`**

### E4 — Hex ↔ binario
**`9F2₁₆` → binario:** 9=`1001`, F=`1111`, 2=`0010` → **`100111110010₂`**
**`1011011₂` → hex:** rellenar a grupos de 4: `0101 1011` → **`5B₁₆`**

### E5 — Direccionamiento de memoria
**a)** Memoria de 2048 bytes con direcciones [0,1023] → 1024 direcciones = 2¹⁰ → palabra = 2048/1024 = **2 bytes**.
**b)** Bus de direcciones de 32 bits, palabra de 1 byte → `2³² × 1B` = **4 GB máximos direccionables**.

### E6 — Representar −120₁₀ en 8 bits
- **BSS**: no representable (no admite negativos).
- **MyS**: 120 = `1111000` + bit de signo → **`11111000`**
- **Ca1**: +120 = `01111000`, invierto → **`10000111`**
- **Ca2**: Ca1 + 1 → **`10001000`**

### E7 — Mínima cantidad de bits para −8₁₀
- MyS/Ca1 con n bits llegan a −(2ⁿ⁻¹−1): n=4 llega a −7 → necesitan **n=5**.
- Ca2 llega a −2ⁿ⁻¹: con **n=4** el rango es [−8,+7] → alcanza. (La asimetría de Ca2 regala un negativo extra.)

### E8 — Representación en exceso 128
- **Codificar +5**: 5+128 = 133 → **`10000101`**
- **Codificar −13**: −13+128 = 115 → **`01110011`**
- **Decodificar `10000000`**: 128−128 = **0** (el centro del rango es el cero real).

### E9 — Flags (4 bits): `0101 + 0111`
Suma: `0101+0111 = 1100`.
- **Z=0** (no es todo ceros) · **N=1** (MSB=1)
- **C=0**: como BSS, 5+7=12 ∈ [0,15] ✓ cabe
- **V=1**: como Ca2, 5+7 debería dar +12, pero 12 ∉ [−8,+7] y el resultado se lee −4. Regla de signos: `(+)+(+)=(−)` → overflow.

### E10 — Flags (4 bits): `1101 + 0011`
Suma: `1101+0011 = 1|0000` (acarreo saliente).
- **Z=1** (los 4 bits del resultado son 0) · **N=0**
- **C=1**: como BSS, 13+3=16 ∉ [0,15] → fuera de rango
- **V=0**: como Ca2, −3+3=0 ✓ correcto (signos opuestos nunca desbordan)

### E11 — Flags (8 bits): `10111001 + 10011101`
Suma: `1|01010110`. **Z=0, N=0, C=1** (BSS: 185+157=342 > 255), **V=1** (Ca2: −71+(−99)=−170 ∉ [−128,127]; regla: `(−)+(−)=(+)`). **Puede haber C y V a la vez.**

### E12 — Decodificar IEEE 754 (float 32)
`1 | 10000001 | 10100000...0`
- Signo = 1 → negativo
- E = `10000001` = 129 → exponente real = 129−127 = 2 → factor 2² = 4
- Mantisa: `1,101₂ = 1 + 0,5 + 0,125 = 1,625`
- Valor = **−4 × 1,625 = −6,5**

### E13 — Operaciones lógicas bit a bit
- `00010001 AND 01011100 = 00010000` (1 solo donde ambos son 1)
- `01010101 XOR 00000000 = 01010101` (XOR con 0 deja igual)
- Recordar: sin acarreo — no es una suma.

### E14 — Full adder: fila crítica de la tabla
**A=1, B=1, C_in=1** → Suma = 1, C_out = 1 (es `1+1+1 = 11₂`). Construcción: half adder 1 procesa A,B; half adder 2 procesa esa suma parcial con C_in; la OR combina ambos acarreos.

### E15 — Octal → hexadecimal
**Convertir `13725₈` a hexadecimal:** octal → binario con 3 bits por dígito: `001 011 111 010 101` → reagrupar de a 4 desde la derecha: `0001 0111 1101 0101` → **`17D5₁₆`**. (Resultado de 15 bits `001011111010101`.)

### E16 — Negativos en distintos sistemas
- **MyS** `1011100`: signo 1 → negativo; módulo `011100` = 16+8+4 = 28 → **−28**.
- **Ca1** de +83 (módulo de 7 bits): `1010011 → 0101100` (= 44); comprobación: 83+44 = 127.
- **Ca2** −3 en 4 bits: `0011 → 1100 → 1101`. Verificación: `1101+0011 = 1|0000` → el acarreo se descarta con 4 bits, resultado `0000` y Z=1.
- **Ca2** −5 en 6 bits: `000101 → 111010 → 111011`.
- **Secuencia en Ca2 de 4 bits**: −1=`1111`, −2=`1110`, −3=`1101`, −4=`1100`, −5=`1011`, −6=`1010`, −7=`1001`, −8=`1000`.

### E17 — Flags: cancelación (8 bits) `11001110 + 00110010`
Suma: `1|00000000`. **Z=1, N=0, C=1** (BSS: 206+50=256 > 255), **V=0** (Ca2: −50+50=0; signos opuestos nunca desbordan).

### E18 — Aritmético vs. procesador (4 bits) `1101 + 1100`
Resultado aritmético: `11001`. Resultado de procesador: `1001` con **C=1**. Si el enunciado pide "el resultado que guarda la ALU", se responde `1001`.

### E19 — Full adder completo y circuito combinacional
| A | B | C_in | S | C_out |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

**Circuito**: `U=NOT A; V=NOT B; W=B AND C; X=NOT(V OR W)`. Con 3 entradas hay 2³=8 filas; método: una columna intermedia por compuerta. Resultado: **X=1 solo cuando B=1 y C=0** (A no interviene).

---

## Consejos para el examen

Provienen de la revisión del primer parcial en la Clase 7 ([[fuentes/arquitectura-computadoras-clase7-apunte-uade]]) y de las Clases 5 y 6:

- Los errores fueron sobre todo **conceptuales**: en los temas teóricos se pide una **definición clara, no un desarrollo extenso**.
- Dificultades frecuentes: el **ciclo de instrucción** (qué hace cada uno de los 4 pasos, definible en una línea) y las **interrupciones** (un llamado externo al procesador, y conocer sus tipos).
- Temas teóricos mencionados antes del parcial: instrucciones, interrupciones y **Von Neumann vs. Harvard**.
- **Seguir la consigna**: no responder lo que no se pidió; intentar "demostrar que se sabe" temas fuera de la consigna hace perder precisión.
- Escribir **primero el apellido y después el nombre**.
- En aritmética binaria **no alcanza con escribir los bits**: justificar con flags y aclarar el sistema de representación.
- En el apunte de la Clase 6 figuran los términos "Lectura", "BCCs" y "ejercicios sobre el cargador" como temas del parcial; son ininteligibles y conviene confirmarlos con el docente.

---

## Checklist final antes del parcial

- [ ] Sé despejar las tres fórmulas eléctricas (`V=I×R`, `P=V×I=I²R`, `Q=P×t`)
- [ ] Recito el ciclo de instrucción: **Fetch → Decode → Execute → Write-back**
- [ ] Distingo los 3 buses y sé usar `Tamaño = 2ⁿ × Palabra`
- [ ] Convierto entre decimal/binario/hex sin calculadora (incluyendo fracciones)
- [ ] Reproduzco la tabla de rangos de los 5 sistemas para cualquier n
- [ ] Aplico la regla de signos para V y sé que **C ↔ BSS, V ↔ Ca2**
- [ ] Justifico **siempre con flags** los ejercicios de fuera de rango
- [ ] Decodifico un float IEEE 754 paso a paso
- [ ] Sé las tablas de verdad de las 7 compuertas
- [ ] Explico half adder → full adder → sumador de 8 bits → ALU con multiplexor
- [ ] Distingo XOR de XNOR por su fórmula y completo la tabla del full adder con C_out
- [ ] Paso de octal a hex pasando por binario y agrupo siempre desde la derecha
- [ ] Distingo resultado aritmético de resultado de procesador (con C)
- [ ] Defino en una línea el ciclo de instrucción y las interrupciones, y sé Von Neumann vs. Harvard

## Referencias

- Fuentes: [[fuentes/arquitectura-computadoras-clase1-uade]] · [[fuentes/arquitectura-computadoras-clase2-uade]] · [[fuentes/arquitectura-computadoras-clase3-uade]] · [[fuentes/arquitectura-computadoras-clase4-uade]] ([[fuentes/arquitectura-computadoras-clase4-notas-uade|notas]], [[fuentes/arquitectura-computadoras-clase4-apunte-uade|apunte]]) · [[fuentes/arquitectura-computadoras-clase5-uade]] ([[fuentes/arquitectura-computadoras-clase5-notas-uade|notas]], [[fuentes/arquitectura-computadoras-clase5-apunte-uade|apunte]]) · [[fuentes/arquitectura-computadoras-clase6-uade]] ([[fuentes/arquitectura-computadoras-clase6-notas-uade|notas]], [[fuentes/arquitectura-computadoras-clase6-apunte-uade|apunte]]) · [[fuentes/arquitectura-computadoras-clase7-apunte-uade]] (revisión del parcial)
- Mapa del curso: [[analisis/estructura-curso-arquitectura-computadoras-uade]]
- Conceptos: [[conceptos/electricidad-basica]] · [[conceptos/semiconductores-y-transistores]] · [[conceptos/ley-de-moore]] · [[conceptos/historia-de-la-computacion]] · [[conceptos/arquitectura-von-neumann]] · [[conceptos/arquitectura-harvard]] · [[conceptos/componentes-de-la-cpu]] · [[conceptos/buses-de-sistema]] · [[conceptos/interrupciones]] · [[conceptos/sistemas-de-numeracion]] · [[conceptos/representacion-numeros-enteros]] · [[conceptos/flags-del-procesador]] · [[conceptos/punto-flotante-ieee754]] · [[conceptos/pipelining-y-superescalaridad]] · [[conceptos/cisc-y-risc]] · [[conceptos/compuertas-logicas]] · [[conceptos/alu-de-1-bit]]
