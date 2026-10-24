---
titulo: "Cómo Leer las Especificaciones de un Procesador"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [especificaciones, intel, amd, turbo, nucleos-hibridos, binning, tp]
fuentes: [arquitectura-computadoras-clase7-apunte-uade]
---

# Cómo Leer las Especificaciones de un Procesador

Criterio para el TP de data center ([[fuentes/arquitectura-computadoras-clase7-apunte-uade]]). Usar siempre las **páginas oficiales** del fabricante y separar marketing de especificación técnica. El nombre comercial (ej. "Ultra 7") solo indica una posición relativa: dos laptops "Ultra 7" pueden tener procesadores muy distintos.

## Líneas de producto

| Segmento | [[entidades/intel]] | [[entidades/amd]] |
|---|---|---|
| PC / gaming | Core, Core Ultra | Ryzen |
| Servidores / estaciones | Xeon | EPYC |
| Bajo consumo | Atom | Embedded |

Los procesadores de servidor mantienen x86 pero con set ampliado (seguridad, escalabilidad), priorizan estabilidad y no usan overclocking.

## Binning y chiplets

Una serie se fabrica junta y produce 20-40 variantes. Como la fabricación nunca es perfecta, los chips se catalogan por calidad real (**binning**): los mejores van a la gama alta; los de menos núcleos funcionales, menor velocidad o sin NPU, a gamas inferiores. AMD suma **chiplets**: uno que no sirve para un Ryzen 9 puede venderse como modelo inferior. Ver [[conceptos/fabricacion-de-microprocesadores]].

## Núcleos e hilos

- **Híbrido** (Intel, Apple): P-core (tareas pesadas), E-core (eficiencia), LP E-core (tareas livianas). El procesador convierte las instrucciones CISC en microinstrucciones simples, con modelo interno tipo RISC ([[conceptos/cisc-y-risc]]).
- **AMD**: núcleos uniformes, todos grandes y con dos hilos (12 núcleos = 24 subprocesos).
- **Hyper-Threading**: un núcleo maneja dos hilos como si fueran dos procesadores.

## Frecuencia y potencia

- **Turbo máximo**: pico de un solo núcleo, no uniforme; depende de refrigeración, placa, BIOS y carga. El apunte lo estima "80 % marketing y 20 % realidad". En uso cotidiano los núcleos trabajan mucho más abajo (ej. P-cores ~2,6 GHz). Para uso general basta la frecuencia **base**.
- **Potencia base vs. turbo** (ej. 25 W vs. 80 W): el consumo y el calor se triplican. El disipador debe soportar la máxima potencia sostenida; si no, hay **throttling** o apagados.
- **Overclocking**: más voltaje o frecuencia; sube consumo y temperatura, puede dañar el chip e invalida la garantía.

## Otras filas de la ficha

| Parámetro | Qué indica |
|---|---|
| Caché L2/L3 | Memoria rápida; no evaluarla aislada ([[conceptos/localidad-y-cache-de-procesadores]]) |
| Litografía | Proceso de fabricación (ej. 18A de Intel) |
| Memoria máxima y tipo | RAM que reconoce el procesador (DDR5 no usa DDR4); puede ser menor que la que admite la placa |
| MT/s | Millones de transferencias por segundo (la RAM no se mide en Hz) |
| Canales de memoria | Ancho de banda procesador-memoria |
| NPU | Se mide en **TOPS** (típicamente INT8) |
| PCIe | Versión (4.0, 5.0): líneas y velocidades |
| Socket | Compatibilidad física para reemplazar el procesador |
| Temperatura máx. | Define el disipador (ej. 100 °C) |

## Datos a verificar

- Core Ultra 7 368H: 6 P + 8 E + 4 LP E suman 18, pero figura con 16 núcleos y 16 hilos.
- Windows (Home, Pro, Server) no cambia el set de instrucciones: lo define la CPU. "Intel CityBoost" probablemente sea Turbo Boost.
- Apple: las variantes "Ultra" unen dos chips Max; la serie M5 se anuncia con 3 nm, no 2 nm.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
- [[conceptos/tipos-de-procesadores]]
- [[conceptos/dual-channel-y-fichas-de-memoria]] — la misma lógica de ficha aplicada a la RAM
- [[conceptos/pci-express]] — versión y carriles que soporta el procesador; el techo del sistema
- [[analisis/tp-data-center-arquitectura-computadoras]] — cómo se usa la ficha en el TP
