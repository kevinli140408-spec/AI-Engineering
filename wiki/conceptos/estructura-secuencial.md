---
titulo: "Estructura de Control Secuencial"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [estructuras-de-control, secuencial, python]
fuentes: [algoritmos-secuenciales-mm, guia-estudio-algoritmia-mm]
---

# Estructura de Control Secuencial

Serie de acciones que se ejecutan **una seguida de la otra**, de arriba hacia abajo. Luego de ejecutar una instrucción, el control pasa a la siguiente. Es la estructura de control más básica de un [[conceptos/algoritmo|algoritmo]].

## Ejemplo: suma de dos números

```python
nro1 = int(input("Ingrese un número: "))
nro2 = int(input("Ingrese un número: "))
suma = nro1 + nro2
print("La suma es:", suma)
```

Todas las instrucciones se ejecutan **una sola vez** y el programa finaliza.

## Relación con otras estructuras
Es la base sobre la que se construyen las estructuras de [[conceptos/estructura-condicional|control condicional]] y [[conceptos/estructura-iterativa|control iterativa]], que alteran el flujo lineal mediante decisiones y repeticiones.

## Referencias

- [[fuentes/algoritmos-secuenciales-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[conceptos/variable-programacion]]
