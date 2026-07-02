---
titulo: "Conjuntos (Sets)"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [conjuntos, set, python, estructuras-de-datos]
fuentes: [introduccion-a-la-programacion-con-python-3]
---

# Conjuntos (Sets)

Colección de elementos **sin duplicados** ni orden garantizado, con operaciones propias de la teoría de conjuntos (unión, intersección, diferencia, inclusión). Se diferencia de una [[conceptos/listas-python|lista]] precisamente en que un elemento no puede aparecer más de una vez.

## Como ejercicio de diseño de clases
[[fuentes/introduccion-a-la-programacion-con-python-3]] usa `Conjunto` como ejercicio guiado de [[conceptos/programacion-orientada-a-objetos|programación orientada a objetos]]: se construye una clase desde cero, almacenando internamente los elementos en una lista y comprobando en cada `inserta` si el elemento ya está presente (`if not elemento in self.elementos`) antes de añadirlo. Sobre esa base mínima se definen métodos como `talla`, `pertenece`, `unión`, `intersección`, `diferencia` e `incluye` — cada uno construido combinando recorridos (`for elemento in ...`) y el operador `in`.

```python
class Conjunto:
    def __init__(self):
        self.elementos = []

    def inserta(self, elemento):
        if elemento not in self.elementos:
            self.elementos.append(elemento)

    def unión(self, otro):
        C = Conjunto()
        C.elementos = self.elementos[:]
        for elemento in otro.elementos:
            C.inserta(elemento)
        return C
```

## El tipo `set` nativo de Python
Python ya incorpora un tipo de datos `set` con exactamente estas garantías y operaciones, optimizado internamente (basado en tablas hash, con pertenencia en tiempo casi constante):
```python
a = {1, 2, 3}
b = {2, 3, 4}
a | b   # unión: {1, 2, 3, 4}
a & b   # intersección: {2, 3}
a - b   # diferencia: {1}
a <= b  # ¿a es subconjunto de b?
2 in a  # pertenencia
```
El ejercicio de construir `Conjunto` a mano tiene valor pedagógico (practicar clases, `self`, listas), pero en un programa real se debe preferir el `set` nativo por rendimiento y por evitar reinventar una herramienta ya probada del lenguaje.

## Referencias
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/listas-python]]
- [[conceptos/mutabilidad-y-referencias]]
- [[conceptos/diccionarios-python]]
