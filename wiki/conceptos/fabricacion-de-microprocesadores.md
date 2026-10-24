---
titulo: "Fabricación de Microprocesadores"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [fabricacion, silicio, oblea, fotolitografia, semiconductores]
fuentes: [arquitectura-computadoras-clase7-apunte-uade]
---

# Fabricación de Microprocesadores

Los chips se construyen sobre **silicio** (de la arena de cuarzo) en láminas llamadas **obleas**. Al ser semiconductor, según el tratamiento conduce o aísla la corriente: ideal como soporte de millones de transistores ([[conceptos/semiconductores-y-transistores]]).

## Etapas

| Etapa | Qué ocurre |
|---|---|
| 1. Cristal de silicio | Silicio policristalino a ~1420 °C en un crisol con gas argón; se hace girar el silicio fundido para formar un monocristal perfecto (según el video, ~200 kg y 200 mm de diámetro) |
| 2. Corte y pulido | Se corta en obleas y se aplana con CMP (Chemical Mechanical Planarization) hasta una rugosidad < 0,1 nm |
| 3. Diseño | El circuito se diseña con software CAD |
| 4. Fotolitografía | La oblea se cubre con fotorresistente y se proyecta el plano del circuito; al retirar los químicos, el diseño queda grabado. Se repite a escala masiva |
| 5. Capas e interconexión | Capas aislantes, zanjas grabadas y rellenas para formar los conductores que unen los transistores en múltiples niveles |
| 6. Encapsulado | El chip se monta en una estructura protectora y funcional: pasa a ser un producto comercial |

## Condiciones de fabricación

- **Contaminación**: una partícula de polvo puede arruinar un chip. Se trabaja en salas limpias, con personal en trajes especiales y duchas de aire.
- **Luz**: los fotorresistentes se destruyen con luz blanca; se usa iluminación amarilla.
- **Pureza**: el silicio debe alcanzar 99,99999999 %; las impurezas obligan a descartar el chip.
- **Automatización**: el proceso dura unos 3 meses y ningún humano toca la oblea (la mueven robots, en lotes de ~25).
- **Estabilidad**: la planta se diseña contra vibraciones; un temblor puede arruinar decenas de miles de obleas.

## Densidad de transistores

Los transistores funcionan como interruptores; cuanto más juntos, más rápido y eficiente es el chip (la corriente recorre menos). Se compara con una ciudad de rascacielos: capas apiladas con tal precisión que 1.000 capas serían más finas que una hoja de papel. Ver [[conceptos/ley-de-moore]].

## Cifras a verificar

El apunte marca inconsistencias: pasa de "luz azul" a "luz amarilla" (se conservó amarilla); "más de 4 millones de componentes por oblea" contradice los "100.000 millones de transistores" por chip. Tomarlas como órdenes de magnitud.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
- [[conceptos/geopolitica-de-semiconductores]]
- [[conceptos/especificaciones-de-procesadores]] (binning: por qué una serie tiene tantas variantes)
