---
tipo: concepto
tags: [logica, tablas-de-verdad, conectivas]
source: raw/3. Tablas de verdad.pptx
created: 2026-06-29
aliases: [tablas de verdad]
---

# Tabla de Verdad

Herramienta de la [[conceptos/logica-proposicional]] que consigna todos los valores de verdad posibles de una fórmula proposicional. Permite determinar si un razonamiento es válido y clasificar fórmulas según su comportamiento lógico.

## Summary

Una tabla de verdad asigna todas las combinaciones posibles de verdadero (V) y falso (F) a las variables de una fórmula y calcula el valor resultante. La cantidad de renglones es 2ⁿ, donde n es el número de variables distintas (1 variable → 2 renglones, 2 → 4, 3 → 8, etc.).

## Key Concepts

### Tablas de las conectivas básicas

| Conectiva | Símbolo | Verdadera cuando... |
|-----------|---------|---------------------|
| Negación | ~p | p es falsa |
| Conjunción | p • q | ambas son verdaderas |
| Disyunción incluyente | p v q | al menos una es verdadera |
| Disyunción excluyente | p w q | exactamente una es verdadera |
| Condicional | p → q | no ocurre antecedente V con consecuente F |
| Bicondicional | p ↔ q | ambas tienen el mismo valor de verdad |

### Construcción de tablas complejas

1. **Disponer las combinaciones**: listar bajo cada variable todos los valores de verdad cubriendo todas las combinaciones posibles.
2. **Resolver por alcance**: calcular primero las conectivas de menor alcance y avanzar hacia la conectiva principal.

### Casos de sustitución

Cada renglón de la tabla puede ilustrarse con [[conceptos/proposicion|proposiciones]] del lenguaje natural que tengan los valores de verdad correspondientes. Esto conecta el cálculo formal con la interpretación semántica.

## Relationships

- [[conceptos/logica-proposicional]] — marco formal donde se definen las tablas de verdad
- [[conceptos/proposicion]] — unidad cuyo valor de verdad se tabula
- [[conceptos/clasificacion-proposiciones]] — tipología que resulta de evaluar una tabla completa
- [[conceptos/logica]] — disciplina general a la que pertenece este método

## References

- [[fuentes/tablas-de-verdad-mm]]
