---
titulo: "Programación I — Clase 8: Tratamiento de Errores a través de Excepciones"
tipo: fuente
creado: 2026-09-09
actualizado: 2026-09-09
tags: [python, excepciones, try-except]
---

# Programación I — Clase 8: Tratamiento de Errores a través de Excepciones

Fuente: diapositivas de la materia "Algoritmos y Estructuras de Datos I / Programación I", [[entidades/ricardo-thompson|Lic. Ricardo Thompson]].

## Resumen
Desarrollo completo del [[conceptos/manejo-de-excepciones|manejo de excepciones]] en Python: control preventivo vs. correctivo, sintaxis `try`/`except`, múltiples `except`, cláusulas `else`/`finally`, instrucciones `raise` y `assert`.

## Contenido principal
- Concepto de excepción y contraste entre control de errores preventivo (`if` anticipado) y correctivo (`try`/`except`).
- Tipos de excepción comunes: `ZeroDivisionError`, `ValueError`, `IndexError`, `KeyboardInterrupt`.
- Sintaxis y funcionamiento de `try`/`except`: bloque protegido, propagación a bloques exteriores, excepción no manejada.
- Múltiples `except` (uno por tipo, evaluados en orden), `except` sin tipo como último recurso, agrupar excepciones en una tupla.
- Ejemplo de función `leerentero()` con reintento dentro de un `while True` + `try`/`except`/`break`.
- Cláusula `else` (solo si el `try` no tuvo errores) como alternativa más "pythonizada" al `break` dentro del `try`.
- Cláusula `finally` (se ejecuta siempre; usos: liberar archivos, conexiones, sesiones) — ejemplo de impresión de matriz usando `except IndexError` + `finally` para manejar el salto de fila.
- Instrucción `raise` (relanzar la excepción actual) y `assert <condición>[, mensaje]` (con `AssertionError`), incluido ejemplo con mensajes diferenciados.

## Contraste con el resto de la wiki
[[conceptos/depuracion-y-pruebas]] (originada en el libro de Marzal et al.) ya tenía una introducción breve a `try`/`except`. Se creó [[conceptos/manejo-de-excepciones]] como página dedicada con el desarrollo completo (múltiples `except`, `else`, `finally`, `raise`, `assert`) que no estaba cubierto, y se dejó en `depuracion-y-pruebas` solo un resumen con enlace a la nueva página.

## Referencias

- [[entidades/ricardo-thompson]]
- [[entidades/python]]
- [[conceptos/manejo-de-excepciones]]
- [[conceptos/depuracion-y-pruebas]]
