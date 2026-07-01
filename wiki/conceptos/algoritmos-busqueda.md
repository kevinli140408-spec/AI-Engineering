---
titulo: "Algoritmos de Búsqueda"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [busqueda, algoritmos, listas, python]
fuentes: [orden-busqueda-mm, joyanes-aguilar-fundamentos-de-programacion]
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

Mucho más eficiente que la búsqueda secuencial para listas grandes, a costa de requerir orden previo (ver [[conceptos/algoritmos-ordenamiento]]). También se puede formular de forma [[conceptos/recursividad|recursiva]] (Cap. 14): la condición de salida es `inferior > superior` (no encontrado) o coincidencia con el centro; en caso contrario, se invoca recursivamente sobre la mitad izquierda o derecha según corresponda.

## Comparación

| Método | Requiere orden | Eficiencia |
|--------|:---:|------------|
| Secuencial | No | Recorre hasta O(n) elementos |
| Binaria | Sí | Descarta la mitad en cada paso |

### Número de comparaciones (Joyanes Aguilar)
- Secuencial: en promedio `(n+1)/2` comparaciones; en el peor caso, `n`.
- Binaria: en el peor caso, `log₂(n+1)` comparaciones (p. ej. para n=1.000.000, solo ~20 comparaciones frente a ~500.000 de la secuencial) — la ventaja crece fuertemente con el tamaño de la lista.

## Búsqueda por transformación de claves (hashing)
Un tercer método, que **no requiere que los datos estén ordenados**: una función de conversión `h(clave)` calcula directamente la posición del elemento en el array (en vez de comparar uno por uno o dividir a la mitad). Es la misma técnica de *hash* ya vista en [[conceptos/algoritmos-archivos]] (Cap. 9, archivos directos), aplicada aquí a vectores en memoria.

**Métodos de conversión** comunes: truncamiento (tomar solo algunos dígitos de la clave), plegamiento (partir la clave en trozos y sumarlos), aritmética modular (`h(x) = x mod m`, con `m` preferentemente primo — el más usado), y mitad del cuadrado (`h(x)` = dígitos centrales de `x²`).

**Colisión**: dos claves distintas producen la misma dirección (`h(x1) = h(x2)`). Se resuelve con una zona de excedentes (igual que en archivos) o por **encadenamiento**: cada posición del array apunta a una [[conceptos/listas-python|lista enlazada]] de los elementos que colisionaron ahí (técnica de estructura dinámica, ver Cap. 12).

En Python, el `dict` (diccionario) implementa internamente esta misma idea de tabla hash, por lo que las búsquedas por clave en un diccionario son, en promedio, de complejidad O(1) — mucho más rápidas que recorrer una lista.

## Referencias

- [[fuentes/orden-busqueda-mm]]
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/listas-python]]
- [[conceptos/algoritmos-ordenamiento]]
- [[conceptos/algoritmos-archivos]]
