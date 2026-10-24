---
titulo: "Manejo de Excepciones (try/except)"
tipo: concepto
creado: 2026-09-09
actualizado: 2026-09-09
tags: [excepciones, try-except, python, manejo-de-errores]
fuentes: [introduccion-a-la-programacion-con-python-3, programacion1-excepciones-thompson]
---

# Manejo de Excepciones (try/except)

Una **excepción** es la indicación de un problema ocurrido durante la ejecución de un programa (división por cero, variable no inicializada, subíndice fuera de rango, error de conversión). El control de errores **tradicional** es preventivo (un `if` evita que el error llegue a ocurrir); el manejo de excepciones es **correctivo**: intenta resolver el problema después de que ya ocurrió, separando la lógica normal del programa del código de control de errores — resultando en programas más robustos y legibles.

## Sintaxis básica

```python
try:
    a = int(input("Dividendo? "))
    b = int(input("Divisor? "))
    print(a // b, a % b)
except ZeroDivisionError:
    print("No se puede dividir por cero.")
```

El código entre `try` y `except` es el **bloque protegido**. Si no ocurre ningún error, el `except` se salta. Si ocurre un error, el resto del bloque protegido se omite; si su tipo coincide con el declarado en el `except`, ese bloque se ejecuta y el programa continúa normalmente. Si el error no coincide con ningún `except` disponible, se propaga hacia bloques `try` exteriores; si nadie lo maneja, se convierte en una **excepción no manejada** que detiene el programa.

## Múltiples except
Pueden encadenarse varios `except`, evaluados en orden — cada tipo de excepción solo puede tener **un** bloque `except` propio:

```python
except ZeroDivisionError:
    print("No se puede dividir por cero")
except ValueError:
    print("Sólo se permiten números enteros")
except:
    print("Error desconocido")   # atrapa cualquier excepción no capturada antes; usar solo como último recurso
```

Si varias excepciones reciben el mismo tratamiento, se agrupan en una tupla: `except (ZeroDivisionError, ValueError):`.

## Cláusula `else`
Opcional, se escribe después de todos los `except`. Se ejecuta **solo si el `try` terminó sin excepciones** — útil para separar el código que debe protegerse del código que solo debe correr si todo salió bien (p. ej. un `break` que sale del bucle de reintento solo tras una entrada válida).

## Cláusula `finally`
Opcional; garantiza que un bloque de código se ejecute **siempre**, haya habido error o no (para liberar recursos: archivos, conexiones de red, sesiones de base de datos, etc.). Orden completo posible: `try` → `except` → `else` → `finally`. `finally` puede usarse incluso sin ningún `except`, junto a un `try` solo.

## Instrucción `raise`
Provoca una excepción manualmente. `raise <Excepción>` lanza una excepción específica; `raise` sin argumentos, dentro de un `except`, **relanza** la última excepción capturada (útil para dar al usuario la opción de abortar en vez de reintentar).

## Instrucción `assert`
`assert <condición>` (opcionalmente con `, "mensaje"`) es una afirmación del programador: si la condición es verdadera no pasa nada; si es falsa, lanza `AssertionError` (con el mensaje, si se indicó). Se captura como cualquier otra excepción: `except AssertionError as mensaje: print(mensaje)`. Es una forma compacta de validar una precondición sin escribir un `if` explícito.

## Excepciones comunes
`ZeroDivisionError` (división por cero), `ValueError` (conversión inválida, p. ej. `int("abc")`), `IndexError` (subíndice fuera de rango), `KeyError` (clave inexistente en diccionario), `KeyboardInterrupt` (el usuario presiona Ctrl-C), `AssertionError` (falla un `assert`).

## Referencias

- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[fuentes/programacion1-excepciones-thompson]]
- [[conceptos/depuracion-y-pruebas]]
- [[conceptos/archivos-ficheros]]
- [[entidades/python]]
