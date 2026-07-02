---
titulo: "Estructura de Control Iterativa"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-01
tags: [estructuras-de-control, ciclos, while, for, python]
fuentes: [control-flujo-ciclos-mm, guia-estudio-algoritmia-mm, joyanes-aguilar-fundamentos-de-programacion, introduccion-a-la-programacion-con-python-3]
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

## Variantes en pseudocódigo algorítmico (Joyanes Aguilar)

Joyanes formaliza **cuatro** estructuras repetitivas, dos controladas por entrada (*pretest*) y dos por salida (*posttest*):

| Estructura | Control | Evaluación de condición | Se ejecuta al menos 1 vez | Equivalente Python |
|---|---|---|---|---|
| `mientras...fin_mientras` | Pretest | Antes de cada iteración | No | `while` |
| `hacer...mientras` (do-while) | Posttest | Al final, continúa si es **verdadera** | Sí | No tiene nativo — se simula con `while True:` + `if cond: break` |
| `repetir...hasta_que` | Posttest | Al final, continúa si es **falsa** (sale cuando se vuelve verdadera) | Sí | No tiene nativo — misma simulación, condición invertida |
| `desde...fin_desde` (`para`) | Pretest, conteo fijo | Variable de control con `desde v ← vi hasta vf [inc/dec p]` | Depende del rango | `for ... in range(...)` |

Nótese la diferencia sutil entre `hacer-mientras` y `repetir-hasta_que`: ambos ejecutan el cuerpo al menos una vez (post-test), pero **el primero continúa mientras la condición es verdadera** y **el segundo continúa mientras es falsa** (termina cuando se cumple).

### Sentencias de salto dentro de un bucle
- **`interrumpir`** (equivalente a `break`): fuerza la salida inmediata del bucle, sin esperar a que la condición se evalúe.
- **`continuar`** (equivalente a `continue`): salta el resto del cuerpo y pasa a la siguiente iteración.
- Nota de contraste: la página ya documentaba que la cátedra de Algoritmia/UADE no usa `break` en sus ejercicios (ver "Banderas" arriba) — eso es una **restricción pedagógica del curso**, no una ausencia del lenguaje: Python sí implementa `break`/`continue` de forma nativa, igual que la mayoría de los lenguajes estructurados que describe Joyanes.

### Métodos de terminación de un bucle controlado por datos leídos
1. Preguntar antes de cada iteración si hay que continuar.
2. Usar una lista encabezada por su tamaño (se lee primero cuántos elementos vienen).
3. Usar un **valor centinela** (un dato que no es válido como entrada real, p. ej. `-1` o `'***'`) que marca el final.
4. Detectar el agotamiento de los datos de entrada (fin de archivo).

### Bucles anidados
Un bucle dentro de otro (`para` dentro de `repetir`, `para` dentro de `para`, etc.) — el bucle interno completa **todas** sus iteraciones por cada iteración del externo. Caso típico: tablas de multiplicar o matrices con doble índice (`i`, `j`).

## `for...in` sobre cualquier secuencia (no solo `range`)
El `for...in` de Python recorre cualquier serie de valores, no solo rangos numéricos: `for nombre in ['Ana', 'Luis', 'Eva']:` asigna a `nombre` cada elemento de la lista en cada iteración ([[fuentes/introduccion-a-la-programacion-con-python-3]]). `range(inicio, fin, paso)` es solo el caso más común: genera un objeto "perezoso" (no una lista materializada) con los enteros de `inicio` a `fin` **sin incluir `fin`**, opcionalmente con `paso` (que puede ser negativo, para recorrer en orden descendente).

### El "error Obi-Wan" (off-by-one)
Equivocarse en un extremo de un rango — iterar una vez de más o de menos — es tan frecuente al programar que tiene nombre propio: **error Obi-Wan** ("off by one", que suena parecido a "Obi Wan" Kenobi). `range(a, b)` produce exactamente `b - a` elementos porque `b` queda excluido; olvidar ese detalle es la causa más común de este tipo de error.

## Referencias

- [[fuentes/control-flujo-ciclos-mm]]
- [[fuentes/guia-estudio-algoritmia-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/estructura-condicional]]
- [[conceptos/listas-python]]
