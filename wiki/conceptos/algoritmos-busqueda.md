---
titulo: "Algoritmos de Búsqueda"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [busqueda, algoritmos, listas, python]
fuentes: [orden-busqueda-mm]
---

# Algoritmos de Búsqueda

Procedimientos para determinar si un valor se encuentra dentro de una [[conceptos/listas-python|lista]].

## Búsqueda secuencial
Recorre la lista **elemento por elemento** hasta encontrar el valor buscado o llegar al final (no encontrado). No requiere que la lista esté ordenada.

```python
def buscarValorSecuencial(lista, nro):
    encontrado = False
    i = 0
    while i < len(lista) and encontrado == False:
        if lista[i] == nro:
            encontrado = True
        i = i + 1
    return encontrado
```

Variante equivalente, más compacta:
```python
def buscarValorSecuencial(lista, nro):
    i = 0
    while i < len(lista) and lista[i] != nro:
        i = i + 1
    return i < len(lista)
```

## Búsqueda binaria
Requiere que la lista esté **ordenada**. Procedimiento:
1. Verificar si el elemento del **centro** de la lista es el buscado.
2. Si no, el orden indica hacia qué mitad continuar.
3. Se descarta la otra mitad y se repite sobre la mitad restante.

```
centro = (izq + der) // 2
```

Mucho más eficiente que la búsqueda secuencial para listas grandes, a costa de requerir orden previo (ver [[conceptos/algoritmos-ordenamiento]]).

## Comparación

| Método | Requiere orden | Eficiencia |
|--------|:---:|------------|
| Secuencial | No | Recorre hasta O(n) elementos |
| Binaria | Sí | Descarta la mitad en cada paso |

## Referencias

- [[fuentes/orden-busqueda-mm]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmos-ordenamiento]]
