---
titulo: "Semiconductores y Transistores"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-08-19
tags: [hardware, electricidad, transistores, semiconductores]
fuentes: [arquitectura-computadoras-clase2-uade]
---

# Semiconductores y Transistores

Base física de la electrónica digital: materiales y componentes que permiten construir circuitos capaces de representar los dos estados (0/1) del [[conceptos/sistemas-de-numeracion|sistema binario]]. Continuación de [[conceptos/electricidad-basica]].

## Materiales según su conductividad

- **Conductores** (cobre, oro, plata, aluminio): dejan pasar la corriente con poca resistencia. El oro se usa en contactos críticos (ej. servidores) por resistir la oxidación que degrada al cobre.
- **Aislantes/dieléctricos** (plástico, madera): impiden el paso de la corriente.
- **Semiconductores** (silicio, germanio): conducen o no según condiciones controladas (dopaje, campo eléctrico); son la base de diodos y transistores.

## Componentes pasivos

- **Capacitor**: se comporta como aislante en CC y como conductor en CA; almacena carga.
- **Inductor/bobina**: comportamiento inverso al capacitor. Ambos se usan para "aplanar" la señal en la rectificación CA→CC.
- **Válvula**: componente electrónico antecesor del transistor, usado en las primeras computadoras (ver [[conceptos/historia-de-la-computacion]]).

## Diodo

Componente semiconductor que conduce corriente en un solo sentido (polarización directa) y la bloquea en el sentido opuesto (zona de agotamiento), con terminales **ánodo** y **cátodo**. El LED es un diodo que emite luz al conducir. Un **puente de diodos** rectifica CA en CC pulsante, que luego se aplana con capacitores/inductores — el mecanismo central de cualquier cargador o fuente de alimentación.

## Transistor

Componente semiconductor de tres terminales (**emisor, base, colector**) que actúa como interruptor o amplificador electrónico controlado por una señal eléctrica. Inventado en 1947 en los **Bell Labs**. Es la pieza fundamental de toda la electrónica digital moderna: un transistor en estado de "circuito cerrado" o "circuito abierto" es la implementación física del **álgebra de Boole**, y por lo tanto del bit (1/0) — ver [[conceptos/sistemas-de-numeracion]] y [[conceptos/componentes-de-la-cpu]].

La cantidad de transistores que pueden integrarse en un chip, y su miniaturización progresiva, es el eje de la [[conceptos/ley-de-moore|Ley de Moore]] y de toda la [[conceptos/historia-de-la-computacion|evolución histórica de la computación]].

## Referencias
- [[fuentes/arquitectura-computadoras-clase2-uade]]
- [[conceptos/electricidad-basica]]
- [[conceptos/ley-de-moore]]
- [[conceptos/componentes-de-la-cpu]]
- [[conceptos/sistemas-de-numeracion]]
