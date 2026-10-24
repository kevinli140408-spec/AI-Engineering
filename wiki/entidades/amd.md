---
titulo: "AMD"
tipo: entidad
creado: 2026-10-24
actualizado: 2026-10-24
tags: [empresa, hardware, x86, procesadores]
fuentes: [arquitectura-computadoras-clase7-apunte-uade]
---

# AMD

Fabricante estadounidense de procesadores x86 que apareció junto a [[entidades/intel]] en los años 80; ganó la disputa legal por la marca "x86" (un número no puede ser marca registrada) — ver [[conceptos/cisc-y-risc]]. Hoy **diseña** sus chips y encarga la fabricación a [[entidades/tsmc]] ([[conceptos/geopolitica-de-semiconductores]]).

- **Líneas**: Ryzen (equivale a Core) y EPYC (equivale a Xeon); embebidos para bajo consumo. Su web se organiza por casos de uso (gaming, producción) más que por modelos ([[conceptos/especificaciones-de-procesadores]]).
- **Chiplets**: divide el procesador en piezas menores; da flexibilidad ante defectos y permite muchas combinaciones sin diseñar un chip nuevo (ej. arquitectura Zen, ver [[conceptos/ley-de-moore]]).
- **3D V-Cache**: apilamiento vertical de mucha caché (90 o 120 MB), pensado para gaming ([[conceptos/localidad-y-cache-de-procesadores]]).
- **Núcleos uniformes**: todos grandes y con dos hilos (12 núcleos = 24 subprocesos), a diferencia de los híbridos de Intel y Apple.
- Integra la interfaz de E/S y NPU en sus SoC ([[conceptos/tipos-de-procesadores]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
