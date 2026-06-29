---
titulo: "Lógica de Predicados"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [logica, predicados, cuantificadores]
fuentes: [logica-predicados-mm]
---

# Lógica de Predicados

Extensión de la [[conceptos/logica-proposicional]] que permite analizar la **estructura interna** de las [[conceptos/proposicion|proposiciones]]: individuos, predicados y cuantificadores. Resuelve casos que la lógica proposicional declara inválidos por no poder "ver" dentro de las proposiciones.

## Ventajas sobre la lógica proposicional

1. **Repeticiones**: identifica que "Pedro es ingeniero" y "Pedro estudia" hablan del mismo individuo.
2. **Relaciones**: distingue "José vive en el Norte" de "José vive al norte de Pedro" (predicados n-ádicos).
3. **Cantidades**: formaliza "todos", "algunos", "ninguno" con cuantificadores.

## Signos básicos

| Tipo | Símbolos | Función |
|------|----------|---------|
| Letras de predicado | F, G, H... | Propiedades o relaciones |
| Constantes de individuo | a, b, c... | Objetos particulares |
| Variables de individuo | x, y, z | Objetos genéricos |
| Cuantificador universal | (x) | "todos", "cualquiera", "ninguno" |
| Cuantificador existencial | (Ex) | "algunos", "hay", "existe" |

## Proposiciones singulares

Atribuyen predicados a individuos específicos: `Fa` = "José es ingeniero".
- Monádicas: `Fa` (una propiedad)
- N-ádicas: `Fab` (relación entre individuos)

## Proposiciones generales

### Categóricas (un sujeto, un predicado)

| Tipo | Forma | Ejemplo |
|------|-------|---------|
| Universal afirmativa | (x)(Fx → Gx) | Todos los hombres son mortales |
| Universal negativa | (x)(Fx → ~Gx) | Ningún hombre es marciano |
| Existencial afirmativa | (Ex)(Fx • Gx) | Algún hombre es ingeniero |
| Existencial negativa | (Ex)(Fx • ~Gx) | Algún hombre no es ingeniero |

**Regla clave**: universales usan **→**, existenciales usan **•**.

### Complejas
Más de un predicado y no categóricas: `(x)[(Fx • Gx) → Hx]` = "Todo ingeniero argentino es universitario".

## Leyes de intercambio de cuantificadores

| Fórmula | Equivalente |
|---------|-------------|
| ~(x) Fx | (Ex) ~Fx |
| ~(Ex) Fx | (x) ~Fx |
| ~(x) ~Fx | (Ex) Fx |
| ~(Ex) ~Fx | (x) Fx |

## Referencias

- [[fuentes/logica-predicados-mm]]
- [[conceptos/logica-proposicional]]
- [[conceptos/proposicion]]
