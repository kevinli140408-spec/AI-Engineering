---
titulo: "Dual Channel y Fichas Técnicas de Memorias RAM"
tipo: concepto
creado: 2026-10-24
actualizado: 2026-10-24
tags: [memoria, ram, dual-channel, ecc, xmp, expo, kingston, instalacion]
fuentes: [arquitectura-computadoras-clase8-apunte-uade, arquitectura-computadoras-clase9-apuntes-uade]
---

# Dual Channel y Fichas Técnicas de Memorias RAM

Criterios para elegir memoria en el TP de data center ([[fuentes/arquitectura-computadoras-clase8-apunte-uade]]).

## Dual Channel

En lugar de un único bus de 64 bits se usan **dos canales de 64 bits independientes** (128 bits), cada uno con sus propias direcciones; el procesador accede a ambos bancos en simultáneo. Mejor 2 × 8 GB en Dual Channel que 1 × 16 GB: se **duplica el ancho de banda** hacia la memoria. El apunte lo compara con la arquitectura Harvard (dos memorias en paralelo), con diferencias técnicas ([[conceptos/arquitectura-harvard]]).

- **Canales**: Dual (2 módulos), Quad (4) y, en servidores, hasta 8. Cada canal apunta a un módulo físico.
- **Buenas prácticas**: comprar **kits** (módulos diseñados para trabajar juntos, con la misma CAS); los slots del mismo color/grupo activan los canales; mezclar fabricantes o latencias puede no activar Dual Channel.
- **Criterio adoptado (2026-10-24)**: para el parcial y el oral, responder que los módulos deben ser **idénticos en velocidad y CAS** (postura de la cátedra). Como aclaración técnica, en la práctica muchas plataformas funcionan con latencias distintas usando la del más lento, pero con riesgo de inestabilidad. Detalle de las dos posiciones: la Clase 9 exige módulos **idénticos** en velocidad y CAS, porque el sistema está sincronizado con el reloj del procesador y latencias distintas desincronizan los bloques que viajan juntos (ej. 128 bits). La nota de la Clase 8 aclara que en la práctica la mayoría de las plataformas aceptan latencias distintas (usan la del más lento), aunque los kits idénticos siguen siendo lo recomendable por estabilidad. ([[fuentes/arquitectura-computadoras-clase9-apuntes-uade]]).
- **Módulo vs. kit**: el módulo es cada pieza (16, 24, 32, 48 GB); el kit es la suma comprada (32, 48, 64, 96 GB).

## Datos de una ficha (ejemplo Kingston)

Kingston fabrica memoria interna (RAM; línea gaming FURY) y externa (SSD, USB, SD). Datos clave:

| Dato | Detalle |
|---|---|
| Capacidad | De módulo y de kit |
| Velocidad | En **MT/s** (hasta 8800 MT/s = reloj de 4400 MHz) |
| Latencia CAS | Ciclos; en un kit, igual para todos los módulos |
| Voltaje | 1,25 a 1,45 V según modelo; el estándar DDR5 es 1,1 V |
| Temperatura | 0 a 85 °C; el difusor de calor ayuda, pero disipa mucho menos que el de un procesador |
| Chips | De fabricantes de semiconductores (ej. SK Hynix) |
| **Número de parte** | Identificador único del producto |

**Regla de oro**: no basta el nombre comercial; hay que verificar el **número de parte**, porque cada cambio de capacidad, velocidad, configuración (módulo o kit) o perfil genera uno distinto. Glosario: UDIMM / CUDIMM (el apunte transcribió "UBIM" y "QCUBIM"), 2R = dual rank, SO-DIMM = notebooks, M.2 = factor de forma de almacenamiento, NVMe = protocolo de SSD.

## Certificaciones

| Perfil | Plataforma | Garantiza |
|---|---|---|
| **Intel XMP 3.0** | Intel | Velocidad, voltaje y tiempos validados |
| **AMD EXPO** | AMD | Lo mismo en sistemas AMD |

Antes de comprar, consultar la velocidad máxima que soporta el procesador ([[conceptos/especificaciones-de-procesadores]]); pagar más velocidad de la que la CPU admite es desperdicio.

## ECC y servidores

**ECC** (Error Correction Code) asegura que los datos escritos sean correctos; crítico donde un error es inaceptable (transacciones bancarias), a diferencia de un videojuego, donde sería un cierre inesperado. Precisión: el módulo ECC guarda **bits extra de verificación** y corrige errores de 1 bit al leer (códigos tipo Hamming); la descripción del apunte (reintentar y marcar bloque "malo") es una simplificación. Los servidores atienden a muchos usuarios simultáneos y usan módulos certificados de 16 a 128 GB.

## Instalación

Pulsera antiestática conectada a una parte metálica a tierra; liberar los brazos para extraer; alinear la muesca (*notch*) sin forzar; presionar hasta el "clic"; un módulo por canal. El primer arranque puede tardar y avisar que cambió la memoria.

## Referencias
- [[fuentes/arquitectura-computadoras-clase8-apunte-uade]]
- [[conceptos/ddr-y-rendimiento-de-ram]]
