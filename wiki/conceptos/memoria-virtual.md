---
titulo: "Memoria Virtual"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, memoria-virtual, paginacion, sistema-operativo]
fuentes: [arquitectura-computadoras-clase8-apunte-uade, arquitectura-computadoras-clase9-apuntes-uade]
---

# Memoria Virtual

La "ilusión de la infinitud": surge cuando la RAM física es insuficiente. En las primeras computadoras la memoria era carísima y se medía en pocos megabytes, lo que dificultaba tener el sistema operativo junto con otras aplicaciones.

## Mecanismo

- El **sistema operativo** toma espacio del disco y lo particiona para que actúe como RAM. Ejemplo: con 500 MB de RAM física se puede llegar a un par de GB de capacidad operativa.
- **Paginación**: el SO crea pedazos direccionables (páginas) en el almacenamiento y trata al disco como extensión de la memoria física.
- **Compromiso**: permite ejecutar aplicaciones que de otro modo no abrirían, pero es mucho más lenta que la RAM, porque el medio es un disco fuera del bus principal ([[conceptos/jerarquia-y-clasificacion-de-memorias]]).
- Hoy sigue siendo esencial como "medio de escape" gestionado por el SO: si una aplicación pide más memoria que la disponible, reserva memoria virtual y evita que el equipo se trabe. Su uso es configurable.

Esquema: RAM física (rápida, cara) + espacio en disco (lento, económico) → el SO los combina → memoria virtual.

## Origen

El apunte la ubica en los años 80. El concepto es anterior: la paginación apareció en sistemas de los años 60 (p. ej. la máquina Atlas); en los 80 se popularizó en las PC.

## En dispositivos móviles

- **Samsung**: suele reservar espacios distintos para aplicaciones y para datos.
- **Apple (iPhone)**: un único bloque para aplicaciones y datos.
- La memoria de datos puede ampliarse con microSD; que la tarjeta pueda sumarse a la memoria de aplicaciones depende del modelo y del SO.

Ver también la jerarquía en [[conceptos/componentes-de-la-cpu]] y [[conceptos/organizacion-de-computadoras]] (el SO asigna memoria).

La Clase 9 la presenta como una **capa de abstracción** del SO que hace creer a las aplicaciones que hay más memoria física: el disco es mucho más lento, pero evita que el equipo colapse ([[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]).

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
