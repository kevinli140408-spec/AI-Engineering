---
titulo: "Organización de una Computadora"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [hardware, arquitectura-von-neumann, memoria, procesador]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Organización de una Computadora

Una **computadora** es un dispositivo electrónico que procesa información: recibe datos de entrada, los procesa y produce datos de salida (resultados). Se compone de dos partes: **hardware** (equipo físico) y **software** (programas) — ver [[conceptos/lenguajes-de-programacion]].

## Arquitectura de Von Neumann
Diseño propuesto en 1946 por John von Neumann: el programa y los datos se almacenan juntos en la memoria de la computadora ("programa almacenado"), en vez de fijarse por cableado físico como en el ENIAC (1946). Es la base de las computadoras digitales actuales — desarrollo completo (ciclo de instrucción, cuello de botella) en [[conceptos/arquitectura-von-neumann]]. Cinco componentes principales:

1. **Dispositivos de entrada** — teclado, ratón, escáner...
2. **Unidad Central de Proceso (UCP/CPU)**, compuesta por:
   - **Unidad de Control (UC)**: dirige la ejecución de instrucciones.
   - **Unidad Aritmético-Lógica (UAL)**: realiza cálculos y comparaciones.
3. **Memoria principal (central)** — almacenamiento de trabajo, rápido pero volátil.
4. **Memoria secundaria (externa)** — almacenamiento masivo, permanente.
5. **Dispositivos de salida** — monitor, impresora...

## Memoria principal
- **RAM** (Random Access Memory): volátil, almacena programas y datos en ejecución; se pierde al apagar la computadora.
- **ROM** (Read Only Memory): permanente, no modificable; almacena programas básicos de arranque.
- **Caché**: memoria intermedia de alta velocidad entre la UCP y la RAM.

Cada posición de memoria (**celda**) tiene una **dirección** única y un **contenido**. Una celda de 8 bits es un **byte**, la unidad mínima para codificar un carácter — ver [[conceptos/representacion-de-la-informacion]].

## Unidades de medida
| Unidad | Equivalencia |
|---|---|
| Byte (B) | 8 bits |
| Kilobyte (KB) | 1.024 B (2¹⁰) |
| Megabyte (MB) | 1.024 KB |
| Gigabyte (GB) | 1.024 MB |
| Terabyte (TB) | 1.024 GB |

## Memoria secundaria (almacenamiento masivo)
No volátil; conserva datos y programas aunque se apague la computadora. Tecnologías: discos magnéticos (discos duros), discos ópticos (CD/DVD) y memorias flash/USB. Los datos se organizan en **archivos (ficheros)**, tema que retoma el libro en el capítulo 9 (pendiente de ingesta).

## Dispositivos de Entrada/Salida (periféricos)
Permiten la comunicación usuario-computadora. Se conectan mediante **buses** (canales de datos) y **conectores/puertos**: USB (Universal Serial Bus, el más extendido) y Firewire (IEEE 1394, alta velocidad).

## Clasificación de computadoras
De menor a mayor capacidad de proceso: personales (PC), estaciones de trabajo, servidores, minicomputadoras, mainframes (grandes computadoras) y supercomputadoras (múltiples procesadores en paralelo; uso científico/militar).

## Software: sistema vs. aplicación
- **Software del sistema**: gestiona los recursos de la computadora — el **sistema operativo** (Windows, Linux, Mac OS), editores de texto, compiladores/intérpretes y utilidades.
- **Software de aplicación**: resuelve tareas específicas del usuario (procesadores de texto, hojas de cálculo, etc.).

El **sistema operativo** asigna memoria, gestiona dispositivos de E/S y planifica el uso de la UCP. Puede ser mono o multiusuario, mono o multitarea (**multiprogramación**: varios programas comparten la UCP por turnos) o **multiproceso** (varias UCP trabajan en paralelo).

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/lenguajes-de-programacion]]
- [[conceptos/representacion-de-la-informacion]]
- [[conceptos/redes-y-web]]
- [[conceptos/arquitectura-von-neumann]]
