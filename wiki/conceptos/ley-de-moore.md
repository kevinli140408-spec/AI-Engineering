---
titulo: "Ley de Moore"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-08-19
tags: [hardware, historia-computacion, intel, transistores]
fuentes: [arquitectura-computadoras-clase2-uade]
---

# Ley de Moore

Observación empírica formulada en 1965 por [[entidades/gordon-moore]], cofundador de Intel: la cantidad de transistores en un circuito integrado, al menor costo por componente, se duplica aproximadamente cada dos años. No es una ley física sino una tendencia de la industria que funcionó como objetivo autocumplido durante décadas.

## Evolución de transistores por generación (ejemplos citados en el curso)

| Procesador | Año | Transistores (aprox.) |
|---|---|---|
| Intel 4004 | 1971 | 2.300 |
| Pentium | 1993 | 3,1 millones |
| Core 2 Duo | 2006 | 291 millones |
| Core i7 | 2010 | 1.170 millones |
| Apple M1 | 2020 | 16.000 millones |
| Apple M4 Ultra | 2025 | 184.000 millones |
| NVIDIA B200 (GPU) | 2024 | 208.000 millones |

Esta progresión es el hilo conductor de la [[conceptos/historia-de-la-computacion]]: cada salto de miniaturización habilitó procesadores más rápidos, chicos y eficientes, del [[entidades/john-von-neumann|ENIAC]] a los smartphones actuales.

## ¿Sigue vigente?

Es tema de debate activo en la industria: ejecutivos de NVIDIA (Jensen Huang) han declarado públicamente que "la Ley de Moore ha muerto", mientras que Intel sostiene que sigue vigente con matices. El límite es físico: a escalas de 2 nanómetros o menos, efectos cuánticos como el **efecto túnel** dificultan seguir miniaturizando transistores de forma convencional.

## Estrategias de continuidad más allá del transistor plano

Ante el límite físico, la industria compensa con arquitecturas alternativas:
- **Chiplets**: en vez de un único chip monolítico, se combinan varios chips más pequeños interconectados (ej. arquitectura AMD Zen con Infinity Fabric) — ver [[conceptos/componentes-de-la-cpu]].
- **Apilamiento 3D**: acumular capas de transistores en altura en vez de solo en superficie.

## Referencias
- [[entidades/gordon-moore]]
- [[conceptos/historia-de-la-computacion]]
- [[conceptos/semiconductores-y-transistores]]
- [[conceptos/componentes-de-la-cpu]]
