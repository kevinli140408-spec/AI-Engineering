---
titulo: "Método Demostrativo"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [logica, demostracion, reglas-logicas, leyes-logicas]
fuentes: [metodo-demostrativo-mm]
---

# Método Demostrativo

Método para demostrar la [[conceptos/validez]] de [[conceptos/razonamiento|razonamientos]] sin construir [[conceptos/tabla-de-verdad|tablas de verdad]] completas. Especialmente útil con muchas variables, donde las tablas serían impracticables (2ⁿ renglones).

## Reglas lógicas

Modelos de razonamientos válidos. Se expresan con **meta-variables** (A, B, C) que representan cualquier fórmula.

| Regla | Abreviatura | Esquema |
|-------|:-----------:|---------|
| Modus Ponens | MP | A → B, A ∴ B |
| Modus Tollens | MT | A → B, ~B ∴ ~A |
| Silogismo Hipotético | SH | A → B, B → C ∴ A → C |
| Silogismo Disyuntivo | SD | A v B, ~A ∴ B |
| Simplificación | S | A • B ∴ A (o ∴ B) |
| Conjunción | C | A, B ∴ A • B |
| Adición | AD | A ∴ A v B |

**Restricción**: las reglas se aplican a fórmulas completas, no dentro de paréntesis.

## Leyes lógicas

Expresan **equivalencias** entre fórmulas. Permiten reemplazar una expresión por otra equivalente, incluso **dentro** de paréntesis.

| Ley | Abreviatura | Equivalencia |
|-----|:-----------:|-------------|
| De Morgan | DM | ~(A v B) ↔ ~A • ~B ; ~(A • B) ↔ ~A v ~B |
| Definición de Condicional | DC | (A → B) ↔ (~A v B) |
| Transposición | TR | (A → B) ↔ (~B → ~A) |

## Formato de demostración

Cada paso se justifica indicando premisas usadas y regla/ley aplicada:
```
1. p → q          (premisa)
2. q → r          (premisa)
3. p              (premisa) / r
4. q              de 1 y 3, MP
5. r              de 2 y 4, MP
```

## Referencias

- [[fuentes/metodo-demostrativo-mm]]
- [[conceptos/validez]]
- [[conceptos/logica-proposicional]]
