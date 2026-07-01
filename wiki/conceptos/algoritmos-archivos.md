---
titulo: "Algoritmos de Procesamiento de Archivos"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [archivos, algoritmos, hash, indexacion, algoritmia]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Algoritmos de Procesamiento de Archivos

Algoritmos típicos para procesar [[conceptos/archivos-ficheros|archivos]] según su organización (secuencial, directa, secuencial indexada).

## Procesamiento de archivos secuenciales

**Patrón general** (creación, consulta o copia): abrir → `mientras no fda(f) hacer` (FDA = Fin De Archivo / EOF) → leer registro → procesar/escribir → `fin_mientras` → cerrar.

```
abrir(f, l, nombre_archivo)
mientras no fda(f) hacer
  leer_f_reg(f, registro)
  escribir_reg(registro)     // o la operación correspondiente
fin_mientras
cerrar(f)
```

- **Altas (insertar)**: como el archivo es secuencial, un registro nuevo se añade al final (si no requiere mantener orden) o, si el archivo está ordenado por clave, se reescribe completo en un **archivo auxiliar**, intercalando el nuevo registro en su posición correcta.
- **Bajas (borrar) y modificaciones**: requieren el mismo patrón de **archivo auxiliar**: se lee el archivo original registro a registro, se copian al auxiliar todos los registros *excepto* (baja) o *con el cambio aplicado* (modificación) al que corresponde; al final, el auxiliar reemplaza al original (`borrar` + `renombrar`). Esto es necesario porque un archivo secuencial no permite reescribir "en el medio" sin desplazar todo lo siguiente.

## Procesamiento de archivos directos (aleatorios)

Acceso directo por **índice** (posición = `(índice-1) * tamaño_registro`) o por **transformación de clave** (función *hash*: `posición ← HASH(clave)`).

- **Colisión**: dos claves distintas producen la misma dirección (`HASH(k1) = HASH(k2)`). Se resuelve con una **zona de excedentes/desbordamiento**: si la posición calculada está ocupada, se busca secuencialmente la siguiente posición libre en esa zona.
- Cada registro suele incluir un campo bandera `ocupado` (p. ej. `'*'` = ocupado) para distinguir un registro con datos válidos de uno vacío o dado de baja (baja lógica).
- **Consulta/altas/bajas/modificaciones** siguen el mismo esqueleto: calcular `posi ← HASH(clave)`, leer esa posición, si la clave no coincide y está ocupada, recorrer secuencialmente la zona de excedentes hasta encontrar la clave o un hueco libre.

## Archivos secuenciales indexados

Combina ambas estrategias: un **área de índice** (tabla clave→posición, cargada en memoria, suele recorrerse con [[conceptos/algoritmos-busqueda|búsqueda binaria]] por estar ordenada) + un **área de datos** (registros completos) + una **zona de desbordamiento** para altas. La consulta busca primero la clave en el índice (rápido, en memoria) y luego accede directamente a la posición indicada en el área de datos — evita recorrer todo el archivo como en el modo puramente secuencial, sin la complejidad de calcular un hash.

## Equivalente práctico en Python
Python no distingue formalmente estas organizaciones a nivel de lenguaje: un archivo de texto (`open(...)`) se procesa naturalmente de forma secuencial (`for linea in archivo:`), y el acceso "directo" se logra con `archivo.seek(posición)` para posicionar el cursor antes de leer — el programador debe calcular la posición manualmente, igual que en el pseudocódigo de Joyanes.

## Ordenar archivos completos
Cuando el archivo entero necesita quedar ordenado (no solo procesado registro a registro) y no cabe en memoria, se aplican algoritmos de **ordenación externa** mediante partición + fusión repetida — ver [[conceptos/ordenacion-externa]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/archivos-ficheros]]
- [[conceptos/algoritmos-busqueda]]
- [[conceptos/ordenacion-externa]]
