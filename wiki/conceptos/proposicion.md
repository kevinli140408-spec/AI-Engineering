---
titulo: "Proposición"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [logica, proposicion]
fuentes: [logica-mm, simbolizacion-proposiciones-mm, tablas-de-verdad-mm]
---

# Proposición

Oración con [[conceptos/funciones-del-lenguaje|función informativa]] a la que tiene sentido atribuir **verdad o falsedad**. Es la unidad básica de análisis de la [[conceptos/logica]].

## Valor de verdad

Cada proposición tiene un **valor de verdad**:
- **Verdadera**: si se corresponde con el hecho que describe
- **Falsa**: si no se corresponde con él

## Tipos

### Proposiciones simples

No incluyen oraciones con un valor de verdad diferente al de la oración completa. Contienen un único enunciado atómico.

- Ejemplo: "El gato es un felino." (V)

### Proposiciones compuestas

Su valor de verdad está **determinado por el valor de verdad de las proposiciones componentes**, unidas por conectivas lógicas.

| Ejemplo | Componentes | Resultado |
|---------|------------|-----------|
| "El gato es un felino **y** es muy ágil." | V **y** V | **V** |
| "El gato es un felino **y** tiene alas." | V **y** F | **F** |
| "**No es cierto que** José es honesto." | negación de V | **F** |

## Qué NO es una proposición

- Fragmentos sin verbo: "La mesa" (no es oración completa)
- Oraciones expresivas: "Sus heladas palabras congelaron mi alma" (metáfora)
- Oraciones directivas: "Haz bien sin mirar a quién" (imperativo)
- Frases incompletas sin valor de verdad asignable

## Representación formal

En la [[conceptos/logica-proposicional]], las proposiciones simples se representan con **variables** (p, q, r...) y las compuestas se construyen con **conectivas** (•, v, w, ~, →, ↔). Ver [[conceptos/logica-proposicional]] para el sistema completo de simbolización.

## Clasificación por tabla de verdad

Las fórmulas proposicionales se clasifican según el resultado de su [[conceptos/tabla-de-verdad]]: **tautología** (siempre V), **contradicción** (siempre F) o **contingencia** (valores mixtos). Ver [[conceptos/clasificacion-proposiciones]].

## Referencias

- [[fuentes/logica-mm]]
- [[fuentes/simbolizacion-proposiciones-mm]]
- [[fuentes/tablas-de-verdad-mm]]
