---
titulo: "Interrupciones"
tipo: concepto
creado: 2026-08-19
actualizado: 2026-09-15
tags: [hardware, arquitectura-von-neumann, cpu]
fuentes: [arquitectura-computadoras-clase2-uade, arquitectura-computadoras-clase3-uade, arquitectura-computadoras-clase4-notas-uade]
---

# Interrupciones

Mecanismo por el cual la CPU suspende temporalmente la ejecución secuencial normal del [[conceptos/arquitectura-von-neumann|ciclo de instrucción]] para atender un evento que requiere atención inmediata.

## Tipos

- **Hardware**: generadas por un dispositivo periférico (ej. una tecla presionada en el teclado, datos listos en el disco), señalizadas mediante una línea física llamada **IRQ**.
- **Software**: solicitadas explícitamente por un programa mediante una instrucción especial (ej. `INT`) para pedir un servicio del sistema operativo.
- **Internas/excepciones**: generadas por la propia CPU al detectar una condición anómala durante la ejecución (ej. división por cero).

## Cuándo se atienden

El procesador chequea si hay interrupciones pendientes **al final de cada ciclo de instrucción**: entre la fase de escritura (write-back) y el próximo fetch ([[fuentes/arquitectura-computadoras-clase4-notas-uade]]).

## Ciclo de interrupción

1. Ocurre el evento que dispara la interrupción.
2. La CPU **guarda el contexto actual** (contenido de los registros de estado/flags y el contador de programa) en la **pila (stack)**, para poder retomar exactamente donde estaba.
3. Consulta el **vector de interrupciones**, una tabla que asocia cada tipo de interrupción con la dirección de su rutina de atención.
4. Ejecuta la **subrutina de atención** correspondiente.
5. **Recupera el contexto** guardado en la pila y retoma la ejecución del programa original en el punto exacto donde fue interrumpido.

## Por qué importan en la arquitectura de Von Neumann

Las interrupciones son el mecanismo que permite a una CPU que ejecuta instrucciones secuencialmente (ver [[conceptos/arquitectura-von-neumann]]) reaccionar a eventos externos asincrónicos sin tener que estar constantemente revisando ("polling") el estado de cada periférico. Son también la base de la multiprogramación descrita en [[conceptos/organizacion-de-computadoras]]: el sistema operativo usa interrupciones de reloj para repartir el tiempo de CPU entre varios programas.

## Referencias
- [[conceptos/arquitectura-von-neumann]]
- [[conceptos/componentes-de-la-cpu]]
- [[conceptos/organizacion-de-computadoras]]
