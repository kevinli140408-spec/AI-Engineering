---
titulo: "Electricidad Básica Aplicada a Hardware"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-08-19
tags: [hardware, electricidad, ley-de-ohm]
fuentes: [arquitectura-computadoras-clase1-uade, arquitectura-computadoras-clase2-uade]
---

# Electricidad Básica Aplicada a Hardware

Fundamentos físicos que explican cómo llega la energía a una computadora y por qué sus componentes internos requieren corriente continua. Base física de [[conceptos/semiconductores-y-transistores]] y, en última instancia, del bit — ver [[conceptos/sistemas-de-numeracion]].

## Magnitudes básicas (analogía hidráulica)

| Magnitud | Definición | Unidad | Analogía |
|---|---|---|---|
| Tensión/Voltaje (V) | Diferencia de potencial que impulsa el movimiento de electrones | Volt | Presión del agua |
| Corriente/Intensidad (I) | Flujo de electrones | Ampere | Caudal |
| Resistencia (R) | Oposición al paso de la corriente | Ohm (Ω) | Estrechamiento de la cañería |
| Potencia (P) | Energía transferida por unidad de tiempo | Watt | — |

La tensión es siempre una diferencia entre dos puntos, nunca un valor "respecto a la nada".

## Leyes fundamentales

- **Ley de Ohm**: `V = I × R` (y sus despejes `I = V/R`, `R = V/I`).
- **Ley de Potencia**: `P = V × I`; combinada con Ohm, `P = I² × R`.
- **Ley de Joule**: `Q = P × t = I² × R × t` — la energía eléctrica disipada se transforma en calor.

Un **cortocircuito** ocurre cuando la resistencia tiende a cero: la corriente tendería a infinito, provocando sobrecalentamiento. Las protecciones eléctricas (llave térmica/interruptor termomagnético, disyuntor) cortan el circuito ante esta condición.

## Corriente Continua (CC) vs. Alterna (CA)

- **CC**: flujo unidireccional y constante. Es la que consumen internamente todos los componentes electrónicos.
- **CA**: cambia periódicamente de sentido (onda sinusoidal); estándar de distribución domiciliaria (Argentina: 220V/50Hz; EE.UU./México: 110V/60Hz; Europa: ~230-240V/50Hz) por su eficiencia de transporte a distancia mediante transformadores. Disputa histórica entre [[entidades/thomas-edison]] (CC) y [[entidades/nikola-tesla]] (CA).

## Generación y transporte

Cadena de 5 fases: **generación** (ej. central hidroeléctrica: dique → turbina → generador por inducción electromagnética) → **transmisión** en alta tensión (decenas a cientos de miles de volts, para minimizar pérdidas) → **subestación** (transformadores reducen la tensión) → **distribución** en media tensión → **consumo** domiciliario en baja tensión. Los cargadores/fuentes de alimentación cumplen el paso final: rectifican la CA doméstica en la CC que requieren los circuitos (ver [[conceptos/semiconductores-y-transistores]]).

## Compatibilidad de cargadores

Para que un cargador funcione con un dispositivo, su salida (**OUTPUT**) debe ser compatible en tensión, corriente máxima, tipo de corriente, conector y polaridad con lo que el dispositivo requiere; su entrada (**INPUT**) debe tolerar la tensión/frecuencia de la red local. Un cargador de menor potencia que la requerida (ej. 60W ofrecido para un equipo de 100W) cargará más lento o no cargará bajo uso intensivo, sin dañar el equipo. La potencia máxima entregable también depende del estándar del conector (USB 2.0: 2,5W; USB 3.0: 4,5W; USB-C: 15W; USB-C con Power Delivery: hasta 240W).

## Gestión térmica

El calor generado (Ley de Joule) se disipa con disipadores (base de cobre, pasta térmica) o refrigeración líquida. Un mal manejo del calor puede alterar la resistencia de los componentes y, por realimentación, dañar el hardware — ver [[conceptos/componentes-de-la-cpu]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase1-uade]]
- [[fuentes/arquitectura-computadoras-clase2-uade]]
- [[entidades/thomas-edison]]
- [[entidades/nikola-tesla]]
- [[conceptos/semiconductores-y-transistores]]
