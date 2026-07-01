---
titulo: "Relaciones entre Clases: Dependencia, Asociación, Agregación"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [uml, relaciones, asociacion, agregacion, composicion, multiplicidad]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Relaciones entre Clases: Dependencia, Asociación, Agregación

Las [[conceptos/programacion-orientada-a-objetos|clases]] no existen aisladas: UML modela tres tipos de relación estructural entre ellas, ordenadas de más débil a más fuerte (sin contar la herencia — ver [[conceptos/herencia]]): **dependencia**, **asociación** y **agregación/composición**. La fortaleza de una relación depende de cuán acopladas estén las clases implicadas.

## Dependencia
La relación más débil: una clase **usa** o conoce brevemente a otra ("...usa un..."), sin mantener una relación duradera. Se representa con una **línea discontinua** con flecha hacia la clase de la que se depende. Ejemplo: `Ventana` depende de `EventoCerrarVentana`.

## Asociación
Relación estructural más persistente: una clase contiene una referencia (atributo) a objetos de otra clase. Se representa con una **línea continua**, opcionalmente con nombre (normalmente un verbo) y dirección de navegabilidad (flecha).

- **Multiplicidad**: cantidad de objetos de una clase que se asocian con un objeto de la otra (`1`, `0..1`, `*`, `0..*`, `1..*`, `m..n`). Por defecto es `1` si no se indica.
- **Restricciones**: reglas adicionales entre llaves cerca de la línea, p. ej. `{ordered}`, `{or}`, `{xor}`.
- **Asociación cualificada**: reduce una multiplicidad uno-a-muchos a uno-a-uno mediante un calificador/identificador (p. ej. número de cuenta), representado como un pequeño rectángulo junto a la clase.
- **Asociación reflexiva**: una clase se asocia consigo misma cuando sus objetos pueden jugar distintos roles (p. ej. `Persona` como `Piloto`/`Pasajero`).
- **Clase de asociación**: una clase puede conectarse (línea punteada) a la propia asociación, no a sus extremos, para agregar atributos/operaciones al vínculo (p. ej. `Contrato` asociado a la relación `Jugador`-`Equipo`).
- **Asociación ternaria**: asocia tres clases simultáneamente, representada con un rombo.
- **Diagrama de objetos**: igual notación que el diagrama de clases, pero muestra instancias concretas y sus **enlaces** (instancias de una asociación) en un momento dado.

## Agregación
Versión más fuerte de la asociación: relación **"todo-parte"** o **"tiene-un"** (has-a). Se representa con un **rombo vacío** del lado de la clase "todo". Es transitiva, asimétrica, y puede ser reflexiva. Ejemplo: `Computadora` agrega `UnidadCentral`, `Teclado`, `Pantalla`.

### Composición
Caso especial de agregación con restricción adicional: si el "todo" se copia o elimina, sus partes se copian/eliminan con él, y cada parte pertenece a un único todo. Se representa con un **rombo relleno**. Se lee "...es parte de...". Ejemplo: una `Mesa` compuesta por `Superficie` y `Patas` — al eliminar la mesa, desaparecen sus patas.

## Síntesis
| Relación | Fuerza | Notación | Lectura |
|---|---|---|---|
| Dependencia | débil | línea punteada + flecha | "usa un" |
| Asociación | media | línea continua | conexión semántica |
| Agregación | fuerte | rombo vacío | "tiene un" / "todo-parte" |
| Composición | más fuerte | rombo relleno | "es parte de" |

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/uml-diagrama-de-clases]]
- [[conceptos/herencia]]
