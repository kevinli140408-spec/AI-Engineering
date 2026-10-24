---
titulo: "ARM"
tipo: entidad
creado: 2026-09-15
actualizado: 2026-10-24
tags: [empresa, arquitectura, risc, hardware]
fuentes: [arquitectura-computadoras-clase5-uade, arquitectura-computadoras-clase5-notas-uade, arquitectura-computadoras-clase7-apunte-uade]
---

# ARM

**Advanced RISC Machine**: empresa de diseño de procesadores y nombre de la ISA [[conceptos/cisc-y-risc|RISC]] dominante en dispositivos móviles (Android, iOS) y en las Mac con Apple Silicon (serie M).

## Modelo de negocio

ARM **diseña y licencia** arquitecturas de procesador; no fabrica chips. Los clientes (ej. Samsung, Apple, Qualcomm) adaptan los diseños a sus productos —gamas altas con más velocidad, gamas bajas más limitadas— y encargan la fabricación propia o a terceros (ej. fundiciones en Taiwán). Esto estandarizó la base tecnológica de los celulares bajo un modelo altamente escalable.

## Características técnicas

- Tipos de datos de 8/16/32/64 bits (half word = 16, word = 32, double word = 64).
- Enteros con signo en [[conceptos/representacion-numeros-enteros|Ca2]]; punto flotante [[conceptos/punto-flotante-ieee754|IEEE 754]] (en algunos chips implementado por software para ahorrar energía).
- **Endianness configurable** (little o big endian), a diferencia de x86 (solo little endian).
- Pionera en **núcleos heterogéneos** (efficiency/performance cores) como respuesta al límite térmico de ~2014.

Su eficiencia energética (instrucciones simples → menor consumo y calor) explica la autonomía superior de los dispositivos ARM frente a x86 — ver [[conceptos/cisc-y-risc]].

## Avance hacia PC y estaciones de trabajo

Según la Clase 7, ARM ya compite fuera de los móviles: Apple (serie M) en estaciones de trabajo y Qualcomm Snapdragon en PC con soporte nativo de Windows, con más rendimiento por vatio. Se compara con x86 en [[conceptos/tipos-de-procesadores]] y [[conceptos/especificaciones-de-procesadores]]. Datos de Apple a verificar: la serie M usa [[entidades/tsmc]], y las variantes "Ultra" unen dos chips Max.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
- [[fuentes/arquitectura-computadoras-clase5-uade]]
- [[fuentes/arquitectura-computadoras-clase5-notas-uade]]
