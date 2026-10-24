---
titulo: "Rendimiento, Localidad y Caché de Procesadores"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [cache, localidad, rendimiento, multinucleo, prefetch]
fuentes: [arquitectura-computadoras-clase7-apunte-uade]
---

# Rendimiento, Localidad y Caché de Procesadores

Complementa la jerarquía de memoria y la terminología de caché (hit, miss, dirty bit) de [[conceptos/componentes-de-la-cpu]].

## Del GHz al multinúcleo

- Hace unos 10 años se buscaba subir la frecuencia. Pero la potencia crece con el cuadrado de la corriente (`P = I²·R`, ver [[conceptos/electricidad-basica]]) y la temperatura se dispara.
- Solución: varios núcleos a velocidad algo menor, en paralelo. La velocidad del reloj dejó de ser el indicador principal y la **caché** pasó a ser crítica porque alivia los cuellos de botella del flujo de datos ([[conceptos/arquitectura-von-neumann]]).

## Principios de localidad

La RAM se accede por señales de dirección y control; la caché se apoya en dos principios:

| Principio | Idea |
|---|---|
| **Temporal** | Lo usado recientemente vuelve a usarse pronto: se deja lo más cerca posible del núcleo |
| **Espacial** | Datos o instrucciones contiguos se usan juntos: se buscan por cercanía |
| **Prefetch** | Mover ráfagas (bursts) de 50 a 100 instrucciones de la RAM a la caché, en vez de una por una |

## Dos filosofías de caché

| | [[entidades/intel]]: gestión dinámica | [[entidades/amd]]: 3D V-Cache |
|---|---|---|
| Idea | La caché total se reparte entre núcleos según la necesidad de cada uno | Apilamiento vertical de mucha caché física sobre los chiplets (ej. 90 o 120 MB) |
| Ventaja | Adaptabilidad | Gaming: las instrucciones de los juegos caben directo en la caché |
| Desventaja | — | Estructura fija y masiva, menos versátil para otras cargas |

La caché no debe evaluarse aislada: el rendimiento depende del conjunto para la aplicación concreta ([[conceptos/especificaciones-de-procesadores]]).

## Estrategia de mercado

Intel y AMD venden el procesador a integradores (Dell, HP, Lenovo), por eso publican sus características. Apple fabrica sus chips y los integra en sus equipos: no vende procesadores sueltos y los datos técnicos aparecen dentro de las especificaciones del sistema.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]]
- [[fuentes/arquitectura-computadoras-clase5-notas-uade]]
- [[conceptos/jerarquia-y-clasificacion-de-memorias]] — pirámide completa; la caché L3 plana (Intel) frente a 3D (AMD) y su acceso asociativo
- [[conceptos/sram-y-dram]] — por qué la caché es SRAM
