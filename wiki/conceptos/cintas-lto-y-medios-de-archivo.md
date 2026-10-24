---
titulo: "Cintas LTO y Medios de Archivo"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [almacenamiento, lto, cinta, archivo, worm, data-center]
fuentes: [arquitectura-computadoras-clase9-apuntes-uade]
---

# Cintas LTO y Medios de Archivo

## Medios portátiles y ópticos

| Medio | Característica |
|---|---|
| Flash (USB, SD, microSD) | Portables, sin alimentación externa; velocidad limitada por el bus USB ([[conceptos/usb-y-thunderbolt]]) |
| CD | ~700 MB |
| DVD | hasta 4,7 GB |
| Blu-ray / doble capa | 25 GB / 50 GB; algunos son **WORM** (escribir una vez, leer muchas) |

## Cinta LTO (Linear Tape-Open)

- **Acceso secuencial**: la cinta debe recorrer el circuito hasta el punto deseado; no compite en acceso aleatorio ([[conceptos/jerarquia-y-clasificacion-de-memorias]]). En un backup continuo la recuperación es rápida; con datos dispersos, lenta.
- Nació de un consorcio (IBM, HP, Quantum) para unificar formatos incompatibles y evitar el *vendor lock-in*. Roadmap con particionado, cifrado y WORM.
- **Costo y energía**: mucho más barata por TB; una vez grabada no consume energía.
- **Seguridad**: desconectada de la red, es inmune a virus, ransomware y hacking; los drives modernos cifran por hardware.
- **Conservación**: el fabricante garantiza integridad por décadas, pero conviene migrar el contenido cada 5 o 10 años. Un SSD sin energía retiene datos solo meses o pocos años ([[conceptos/discos-hdd-y-ssd]]).
- **Nube**: los niveles de "archivo profundo" (ej. Amazon Deep Archive) usan cinta: costo mínimo, recuperación lenta.
- **WORM**: garantiza inmutabilidad; útil para historias clínicas, movimientos bancarios y cumplimiento normativo.

| Tecnología | Velocidad secuencial | Ventaja | Desventaja |
|---|---|---|---|
| Cinta LTO-10 | ~400 MB/s | Bajo costo, durabilidad, sin consumo | Acceso aleatorio muy lento |
| HDD | 250-320 MB/s | Mejor acceso que la cinta | Más costo por TB y consumo |
| SSD SATA / NVMe | ~6 Gbps / ~7 GB/s | Velocidad muy alta | No apto para retención de décadas sin energía |

Las capacidades por generación (LTO-9: 12 o 18 TB nativos; LTO-10: 45 TB; cifras comprimidas) son inconsistentes en la nota: confirmar en lto.org.

## Escala de data center: librerías robóticas

- Se miden en **petabytes**; las usan Google, Amazon, Dropbox y productoras (Disney, HBO, Netflix).
- **Modelo híbrido**: discos para contenido de acceso inmediato y cintas para originales y copias menos frecuentes; la película empieza a reproducirse mientras se sigue descargando, disimulando la latencia.
- Cada mueble guarda ~400 cintas; un brazo robótico identifica el cartucho por código de barras y se mueve por coordenadas (X, Y, Z); una base de datos indica qué cartucho y qué drive.
- Infraestructura: piso elevado (~30 cm) para cables y refrigeración; el aire frío sube por los equipos y sale caliente por arriba.

## Referencias
- [[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]
- [[conceptos/raid]]
