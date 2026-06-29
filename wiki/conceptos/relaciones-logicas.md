---
titulo: "Relaciones Lógicas"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [logica, relaciones-logicas, tablas-de-verdad]
fuentes: [relaciones-logicas-mm]
---

# Relaciones Lógicas

Vínculos formales entre pares de fórmulas de la [[conceptos/logica-proposicional]], verificables mediante [[conceptos/tabla-de-verdad|tablas de verdad]]. Fundamentales para evaluar la [[conceptos/validez]] de [[conceptos/razonamiento|razonamientos]].

## Las seis relaciones

### 1. Implicación lógica
A **implica** B si en ningún renglón A es V y B es F.
> "Si llueve, el piso se moja" — la lluvia implica piso mojado.

### 2. Deducibilidad
B **se deduce de** A si A implica B. Es la **inversa** de la implicación.

### 3. Equivalencia lógica
A y B son **equivalentes** si se implican mutuamente (tablas idénticas).
> Ejemplo: `~p v q` y `p → q` son equivalentes.

### 4. Contrariedad (incompatibilidad)
A y B son **contrarias** si en ningún renglón resultan **ambas V**.
> No pueden ser verdaderas a la vez, pero sí falsas a la vez.

### 5. Subcontrariedad
A y B son **subcontrarias** si en ningún renglón resultan **ambas F**.
> No pueden ser falsas a la vez, pero sí verdaderas a la vez.

### 6. Contradictoriedad
A y B son **contradictorias** si en ningún renglón resultan ambas V **ni** ambas F.
> En cada renglón, exactamente una es V y la otra F.

## Propiedades especiales

- Una **tautología** es implicada por cualquier fórmula.
- Una **contradicción** implica cualquier fórmula.

## Referencias

- [[fuentes/relaciones-logicas-mm]]
- [[conceptos/logica-proposicional]]
- [[conceptos/tabla-de-verdad]]
- [[conceptos/clasificacion-proposiciones]]
