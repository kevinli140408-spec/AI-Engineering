---
titulo: "TP de Data Center — Arquitectura de Computadoras (síntesis Clases 7-9)"
tipo: analisis
creado: 2026-10-24
actualizado: 2026-10-24
tags: [arquitectura-de-computadoras, tp, data-center, evaluacion, compatibilidad]
fuentes: [arquitectura-computadoras-clase7-apunte-uade, arquitectura-computadoras-clase8-apunte-uade, arquitectura-computadoras-clase9-apuntes-uade]
---

# TP de Data Center — síntesis de las Clases 7, 8 y 9

Síntesis de lo que piden las tres clases sobre el segundo trabajo práctico de [[entidades/uade]]. Cada clase agrega detalle; no hay contradicciones de fondo, pero el escenario se concretó en la Clase 9.

## Evolución de la consigna

| Clase | Qué se dijo |
|---|---|
| 7 ([[fuentes/arquitectura-computadoras-clase7-apunte-uade]]) | Rol profesional en un data center: analizar la aplicación, elegir el tipo de sistema, definir procesador, memoria y almacenamiento. TP grupal + informe + defensa individual |
| 8 ([[fuentes/arquitectura-computadoras-clase8-apunte-uade]]) | "Gerente de data center": listado de compra con justificación, diagrama de red, entrega y defensa |
| 9 ([[fuentes/arquitectura-computadoras-clase9-apuntes-uade]], clase del 2026-10-13) | Plataforma para desarrollar un videojuego (Unity, Unreal u otro), con base de datos y CRM; sin evaluación de costos |

## Qué hay que entregar

1. Listado de equipos con características detalladas de cada componente.
2. **Planilla de compatibilidades**: memoria–procesador y entre todos los componentes.
3. **Justificación técnica** de cada equipo para la carga propuesta.
4. **Diagrama de red** ([[conceptos/nas-san-y-redes-de-almacenamiento]]).

## Criterios técnicos

- **Aplicaciones y SO**: base de datos y CRM por separado (servidor, concurrencia, volumen); consultar la página oficial de cada base de datos y tener en cuenta los usuarios (4 simultáneos no es lo mismo que 10.000). El SO se elige según las aplicaciones: Windows 11 Pro, Windows Server o Linux (ej. Red Hat de 64 bits); entender su rol entre aplicaciones y hardware.
- **Modelo de despliegue**: 100 % local, 100 % nube o híbrido; lo evaluable es el criterio para justificar dónde corre cada aplicación (el entorno de desarrollo, en la PC local; el CRM podría tener su base en la nube).
- **Sobredimensionamiento**: permitido si hay criterio; 32→64 GB no es 64→128 GB. Preferir estándares de la industria.
- **Alcance y usuario**: el tipo de juego define la potencia; definir equipos testigo coherentes con los dispositivos del usuario (PC con GPU, celular, tablet).
- **Compatibilidad**: la RAM no puede superar lo que el procesador direcciona (96 GB soportados, 128 GB configurados → falla); PCIe: versión y carriles ([[conceptos/pci-express]]); tipo de memoria (DDR5 vs. DDR4); número de parte, XMP/EXPO y ECC ([[conceptos/dual-channel-y-fichas-de-memoria]]); almacenamiento según criticidad ([[conceptos/raid]], [[conceptos/discos-hdd-y-ssd]]). Fuente indispensable: la ficha del procesador ([[conceptos/especificaciones-de-procesadores]]).
- Los equipos comerciales (HP, Dell) traen una configuración mínima que no alcanza para todos los casos.
- **Rol del gerente de sistemas**: valida y firma la compra; una mala validación cuesta miles de dólares.

## Evaluación

| Aspecto | Regla |
|---|---|
| Fecha | Sin flexibilidad: el equipo que no entrega en fecha y forma recibe 1; se sugiere entregar una semana antes. Fechas de la Clase 7: entrega del TP el 2026-11-10 y segundo parcial el 2026-11-17 (sin año explícito en el apunte; confirmar) |
| Aprobación | Un TP pobre o con menos del 60 % de los requerimientos no aprueba. La evaluación del TP es por equipo |
| Oral | **Individual**, con preguntas por integrante |
| Nota > 8 | Posibilidad de promoción: conoce la teoría y la aplica al TP |
| Nota 4-7 | Sin promoción: TP aceptable pero sin dominio, o preguntas teóricas generales (ej. jerarquía de memoria) |
| Falla en teoría | Reprueba sin importar la calidad del TP |

No se memorizan modelos exactos (se pueden consultar), pero sí los **criterios de selección**. "Armamos un NAS con 8 discos de 10 TB en RAID 6" no alcanza: hay que explicar la capacidad útil y el porqué.

## Logística

10 equipos (los primeros 5 definidos); ~30 minutos por grupo, posible división en dos tandas. La asistencia se computa ingresando a la facultad y marcando con QR. Próxima clase: el concepto de nube y un método de resolución de problemas.

## Preguntas de autoevaluación (Clase 9)

Las 12 preguntas del apunte cubren DRAM/SRAM, Dual Channel, DDR vs. GDDR/HBM, ancho de banda PCIe, RAM máxima del procesador, bloques y fragmentación, KB vs. KiB, RAID 1/5/6/10, capacidad con 10 × 10 TB, relevancia de LTO, NAS vs. SAN y despliegue local/nube/híbrido.

## Referencias
- [[fuentes/arquitectura-computadoras-clase7-apunte-uade]] · [[fuentes/arquitectura-computadoras-clase8-apunte-uade]] · [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[analisis/estructura-curso-arquitectura-computadoras-uade]]
