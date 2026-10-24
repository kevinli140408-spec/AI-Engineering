---
titulo: "Nikola Tesla"
tipo: entidad
creado: 2026-08-19
actualizado: 2026-08-19
tags: [persona, hardware, historia-computacion, electricidad]
fuentes: [arquitectura-computadoras-clase1-uade, arquitectura-computadoras-clase2-uade]
---

# Nikola Tesla

Ingeniero e inventor serbio-estadounidense (1856-1943), impulsor de la **corriente alterna (CA)** como estándar para la generación y el transporte de energía eléctrica a gran escala — ver desarrollo técnico en [[conceptos/electricidad-basica]].

## Aporte técnico

A diferencia de la corriente continua (CC) promovida por [[entidades/thomas-edison|Thomas Edison]], la CA cambia periódicamente de sentido (onda sinusoidal) y puede elevarse o reducirse de tensión de forma eficiente mediante transformadores. Esta propiedad la hizo la opción ganadora para transportar energía a largas distancias con pérdidas mínimas: se eleva la tensión a valores muy altos (según las fuentes del curso, del orden de 130.000 a 500.000 V) para el transporte, y luego se reduce progresivamente en subestaciones hasta los ~220-230 V del consumo doméstico en Argentina.

## Relevancia para la arquitectura de computadoras

El curso de Arquitectura de Computadoras de [[entidades/uade]] presenta la disputa histórica Tesla-Edison como punto de partida para explicar por qué la energía llega al hogar en CA (220V/50Hz en Argentina) pero los componentes internos de una computadora funcionan en CC: la fuente de alimentación de la PC (o el cargador de una notebook/celular) cumple la función de rectificar la CA de la red en la CC que necesitan los circuitos electrónicos. Este mismo principio de generación/transporte se ilustra con el ejemplo de una central hidroeléctrica (turbina + generador por inducción electromagnética).

## Referencias
- [[fuentes/arquitectura-computadoras-clase1-uade]]
- [[fuentes/arquitectura-computadoras-clase2-uade]]
- [[conceptos/electricidad-basica]]
- [[entidades/thomas-edison]]
