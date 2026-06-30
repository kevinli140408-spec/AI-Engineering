---
titulo: "Lógica Proposicional"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [logica, simbolizacion, conectivas]
fuentes: [simbolizacion-proposiciones-mm, tablas-de-verdad-mm, relaciones-logicas-mm, metodo-demostrativo-mm]
---

# Lógica Proposicional

Lenguaje simbólico de la [[conceptos/logica]] que permite representar [[conceptos/proposicion|proposiciones]] y sus relaciones mediante variables y conectivas, eliminando la ambigüedad del lenguaje natural.

## Signos básicos

| Tipo | Símbolos | Función |
|------|----------|---------|
| Variables proposicionales | p, q, r, s, t... | Representan proposiciones simples |
| Conectivas | •, v, w, ~, →, ↔ | Nexos entre proposiciones |
| Signos auxiliares | ( ), [ ], { } | Precisan alcance de conectivas |

## Las seis conectivas

### 1. Conjunción (•)
Lenguaje natural: "y", "pero", "aunque", "sin embargo".
p • q es verdadera solo si **ambas** componentes son verdaderas.

**Excepción**: "Juan y Pedro son hermanos" expresa una relación → es una proposición simple (p), no una conjunción.

### 2. Disyunción incluyente (v)
Lenguaje natural: "o", "y/o".
p v q es verdadera si **al menos una** componente es verdadera.

### 3. Disyunción excluyente (w)
Lenguaje natural: "o bien... o bien...".
p w q es verdadera si **exactamente una** componente es verdadera. Solo admite dos términos.

### 4. Negación (~)
Lenguaje natural: "no", "no es cierto que".
- "Ni A ni B" = ~A • ~B
- "No es cierto que A y B" = ~(A • B) — atención: **distinto** de ~A • ~B

### 5. Condicional (→)
Lenguaje natural: "si... entonces...", "sólo si", "suficiente/necesaria".

| Expresión | Fórmula | Regla |
|-----------|---------|-------|
| Si p, entonces q | p → q | Directo |
| Sólo si p, q | q → p | **Invertido** |
| Suficiente p para q | p → q | Directo |
| Necesaria p para q | q → p | **Invertido** |

### 6. Bicondicional (↔)
Lenguaje natural: "si y sólo si", "es equivalente".
p ↔ q = (p → q) • (q → p).

## Código y fórmula

El proceso de simbolización requiere:
1. Identificar las proposiciones simples → asignar variables (**código**)
2. Identificar las conectivas y su alcance → escribir la **fórmula**
3. Usar paréntesis para desambiguar (sin ellos, p • q → r es ambigua)

## Herramientas de evaluación

- **[[conceptos/tabla-de-verdad]]**: permite evaluar fórmulas proposicionales asignando todos los valores posibles a sus variables.
- **[[conceptos/clasificacion-proposiciones]]**: toda fórmula se clasifica como tautología, contradicción o contingencia según su tabla de verdad.

## Temas avanzados

- **[[conceptos/relaciones-logicas]]**: implicación, deducibilidad, equivalencia, contrariedad, subcontrariedad, contradictoriedad.
- **[[conceptos/razonamiento]]**: argumentos con premisas y conclusión; simbolización.
- **[[conceptos/validez]]**: evaluación de razonamientos deductivos.
- **[[conceptos/metodo-demostrativo]]**: reglas y leyes lógicas para demostraciones sin tablas.
- **[[conceptos/logica-de-predicados]]**: extensión con predicados y cuantificadores.

## Referencias

- [[fuentes/simbolizacion-proposiciones-mm]]
- [[fuentes/tablas-de-verdad-mm]]
- [[fuentes/relaciones-logicas-mm]]
- [[fuentes/metodo-demostrativo-mm]]
