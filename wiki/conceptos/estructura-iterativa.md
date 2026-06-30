---
titulo: "Estructura de Control Iterativa"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [estructuras-de-control, ciclos, while, for, python]
fuentes: [control-flujo-ciclos-mm, guia-estudio-algoritmia-mm]
---

# Estructura de Control Iterativa

Repite una secuencia de acciones (**iteraciones**) mientras se cumpla una condición lógica. En Python se implementa con `while` y `for`.

## Clasificación de ciclos

### Ciclos exactos (cantidad conocida)
Se conoce de antemano cuántas veces se repite. Controlados por **contador**.

```python
contador = 1
while contador <= 5:
    print(contador)
    contador = contador + 1
```

**Ciclo `for`**: simplifica los ciclos exactos usando `range(m, n, p)`.
```python
for i in range(1, 6):       # 1, 2, 3, 4, 5
    print(i)
```
- `range(n)`: de 0 a n-1.
- `range(m, n)`: de m a n-1.
- `range(m, n, p)`: de m a n-1, saltando de a p (p ≠ 0).

### Ciclos condicionales (cantidad desconocida)
Dependen de cálculos o de un valor centinela ingresado por teclado. Se resuelven con `while`.
```python
suma = 0
num = int(input("Ingrese un número, -1 para finalizar: "))
while num != -1:
    suma = suma + num
    num = int(input("Ingrese un número, -1 para finalizar: "))
print("La suma es", suma)
```

## Variables contadores
Se incrementan/decrementan en una **cantidad fija (constante)**. Requieren inicialización (`cont = 0` o `1`) y un incremento (`cont = cont + 1`) dentro del ciclo.

## Variables acumuladoras (sumadores)
Se incrementan en una **cantidad variable**. Se inicializan en 0 y se actualizan con `suma = suma + valor`.

## Banderas (flags)
Variable booleana (`True`/`False`) que indica si algo ocurrió durante la iteración. *Nota: este curso de Algoritmia/UADE no trabaja ciclos que terminan únicamente por bandera ni usa `break`.*

## Ciclo infinito
Ocurre cuando la condición del `while` nunca se vuelve falsa porque ninguna variable involucrada cambia dentro del ciclo. Es un **error lógico grave** — en exámenes de esta cátedra implica desaprobación automática del ejercicio.

```python
x = 5
while x > 0:
    print("Todavía vale", x)
    x = x - 1   # imprescindible: modifica la condición
```

## Componentes de un ciclo
1. Expresión de inicialización.
2. Condición(es) lógica(s).
3. Acciones a repetir.
4. Condición de terminación (evitar ciclo infinito).
5. Expresión de finalización (qué hacer con el resultado).

## ¿Cuándo usar `for` vs `while`?

| Usar `for` cuando... | Usar `while` cuando... |
|---|---|
| Se conoce la cantidad de repeticiones | No se conoce la cantidad |
| Se recorre una secuencia (`range`, lista, string) | La repetición depende de una condición |
| El control es automático | Se necesita control manual |

## Referencias

- [[fuentes/control-flujo-ciclos-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[conceptos/estructura-condicional]]
- [[conceptos/listas-python]]
