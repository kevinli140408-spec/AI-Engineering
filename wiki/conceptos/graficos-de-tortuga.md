---
titulo: "Gráficos de Tortuga (módulo turtle)"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [python, graficos, turtle, interfaz-grafica]
fuentes: [introduccion-a-la-programacion-con-python-3]
---

# Gráficos de Tortuga (módulo turtle)

Forma sencilla de crear gráficos con Python controlando un "lápiz" virtual (la **tortuga**) mediante órdenes relativas ("avanza 100 pasos", "gira 90 grados a la derecha"). Es el primer contacto del libro [[fuentes/introduccion-a-la-programacion-con-python-3]] con salida gráfica, antes de llegar a interfaces gráficas de usuario completas (el módulo `Tkinter`, sobre el que se apoya `turtle`).

## Origen histórico
El concepto viene del lenguaje **Logo**, diseñado a mediados de los años 60 por Seymour Papert y Wally Feurzeig para enseñar a programar a niños. Logo controlaba un "plotter virtual" representado como un triángulo isósceles (la "tortuga"), de ahí el nombre genérico "gráficos de tortuga" para cualquier sistema inspirado en esta idea.

## Estructura básica de un programa con turtle
```python
from turtle import Screen, Turtle

pantalla = Screen()
pantalla.setup(425, 225)          # tamaño de la ventana
pantalla.screensize(400, 200)     # tamaño de la superficie de dibujo

tortuga = Turtle()
tortuga.forward(100)              # avanza 100 pasos, dejando trazo

pantalla.exitonclick()            # espera un clic para cerrar la ventana
```

## Métodos relativos (dependen de la posición/orientación actual)
- `forward(d)` / `backward(d)`: avanza/retrocede `d` pasos.
- `left(g)` / `right(g)`: gira `g` grados a la izquierda/derecha.
- `penup()` / `pendown()`: levanta/baja el lápiz (para desplazarse sin dejar trazo).
- `pensize(s)` / `pencolor(c)`: grosor del trazo en píxeles / color (cadena con el nombre en inglés).
- `dot(d)`: dibuja un punto de diámetro `d`. `circle(r)`: dibuja un círculo de radio `r` (centrado a `r` pasos a la izquierda de la tortuga). `write(t)`: escribe texto.
- `speed(n)`: velocidad de movimiento (0 = instantáneo, 1 = mínima, 10 = máxima; por defecto 6).
- `hideturtle()` / `showturtle()`: oculta/muestra el triángulo de la tortuga (útil para no "ensuciar" el dibujo final).

## Métodos absolutos (coordenadas/ángulos fijos, no relativos a la tortuga)
- `goto(x, y)`: mueve la tortuga a coordenadas absolutas.
- `setx(x)` / `sety(y)`: fija solo la abscisa/ordenada.
- `setheading(g)`: apunta en dirección absoluta de `g` grados (0° = este).
- `towards(x, y)`: apunta hacia el punto dado. `home()`: vuelve al origen (0,0).
- `setworldcoordinates(x1, y1, x2, y2)` (de `pantalla`): redefine el sistema de coordenadas de toda la superficie de dibujo.

## Caso de uso ilustrativo
El libro construye paso a paso un gráfico de pastel (porcentajes de calificaciones de una asignatura) combinando círculo, líneas radiales y texto — y usa el ejemplo para motivar la necesidad de **funciones** y **estructuras de control**: el programa resultante repite el mismo bloque de órdenes cuatro veces (una por categoría), cambiando solo un par de valores. Ver [[conceptos/funciones-programacion]] y [[conceptos/estructura-iterativa]] para las herramientas que permiten evitar esa repetición.

## Referencias
- [[fuentes/introduccion-a-la-programacion-con-python-3]]
- [[entidades/python]]
- [[conceptos/funciones-programacion]]
- [[conceptos/estructura-iterativa]]
