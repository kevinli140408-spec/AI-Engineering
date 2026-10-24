---
titulo: "Torres de Hanoi"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-09-09
tags: [torres-de-hanoi, recursividad, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion, programacion1-recursividad-thompson]
---

# Torres de Hanoi

Problema clásico de origen oriental, usado tradicionalmente como el ejemplo arquetípico de [[conceptos/recursividad|recursión]] "divide y vencerás". Hay 3 varillas (inicial, central/auxiliar, final) y `n` discos de diámetros distintos apilados en la varilla inicial, de mayor a menor. Reglas:
- Solo se mueve **un disco a la vez**.
- Nunca puede quedar un disco sobre otro **más pequeño**.

El objetivo es trasladar toda la pila a la varilla final. El pasatiempo se presentó en Europa en 1883; la leyenda asociada (monjes de un templo de Brahma en la India moviendo 64 discos de oro, con el fin del mundo llegando al completar la tarea) es la que popularizó el problema como ejemplo de crecimiento exponencial.

## Por qué es recursivo
Mover `n` discos de la varilla inicial a la final se descompone en tres subproblemas más pequeños:
1. Mover los `n-1` discos superiores de la inicial a la **auxiliar** (usando la final como apoyo).
2. Mover el disco más grande (el restante) de la inicial a la **final** directamente.
3. Mover los `n-1` discos de la auxiliar a la **final** (usando la inicial como apoyo).

Los pasos 1 y 3 son, a su vez, el mismo problema con un disco menos — de ahí la recursión. El **caso base** es `n = 1`: mover un único disco directamente.

```
procedimiento Hanoi(E entero: n; E caracter: inicial, final, auxiliar)
inicio
  si n = 1 entonces
    escribir('Mover disco 1 de ', inicial, ' a ', final)
  si_no
    Hanoi(n - 1, inicial, auxiliar, final)
    escribir('Mover disco ', n, ' de ', inicial, ' a ', final)
    Hanoi(n - 1, auxiliar, final, inicial)
  fin_si
fin_procedimiento
```

Nótese que el orden de los parámetros cambia entre las dos llamadas recursivas: la primera usa `final` como varilla auxiliar (paso 1), la segunda usa `inicial` como auxiliar (paso 3) — el "rol" de cada varilla rota en cada nivel de la recursión.

## Equivalente en Python
```python
def hanoi(n, inicial, final, auxiliar):
    if n == 1:
        print(f"Mover disco 1 de {inicial} a {final}")
    else:
        hanoi(n - 1, inicial, auxiliar, final)
        print(f"Mover disco {n} de {inicial} a {final}")
        hanoi(n - 1, auxiliar, final, inicial)
```

## Complejidad
El número mínimo de movimientos necesarios es `2^n - 1`. Crece exponencialmente: 3 discos requieren 7 movimientos, 10 discos requieren 1023, y 64 discos (la leyenda original del templo) requerirían más de 18 trillones de movimientos — en la práctica, intratable más allá de un puñado de discos. Es un buen ejemplo de por qué la elegancia de una solución recursiva no implica eficiencia: el costo está en la naturaleza del problema, no en el algoritmo.

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[fuentes/programacion1-recursividad-thompson]]
- [[conceptos/recursividad]]
- [[conceptos/pilas-y-colas]]
