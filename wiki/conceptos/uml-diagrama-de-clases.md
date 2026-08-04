---
titulo: "Diagrama de Clases UML: Notación de Objetos y Clases"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-07-28
tags: [uml, diagrama-de-clases, objetos, visibilidad, ocl]
fuentes: [joyanes-aguilar-fundamentos-de-programacion]
---

# Diagrama de Clases UML: Notación de Objetos y Clases

Notación gráfica concreta que UML usa para representar [[conceptos/programacion-orientada-a-objetos|objetos y clases]] — continuación directa de lo anticipado en [[conceptos/uml]].

## Representación de un objeto
- Rectángulo con el **nombre del objeto subrayado**: `nombre : Clase` (instancia con nombre) o `:Clase` (instancia anónima).
- Tres "vistas" posibles del icono: solo nombre, nombre + atributos, nombre + atributos + valores actuales.
- Múltiples instancias: icono apilado (varios rectángulos superpuestos).
- Definición de [[entidades/tres-amigos-uml|Booch]]: un objeto = **estado + comportamiento + identidad**. Estado: valores de los atributos en un momento dado. Comportamiento: conjunto de operaciones (lo que el objeto puede hacer, o que se le puede hacer). Identidad: lo distingue de cualquier otro objeto aunque tenga estado idéntico — no se modela explícitamente; se resuelve en la implementación con un identificador (p. ej. número de serie).
- Atributo: `nombre : tipo = valor_por_defecto` (p. ej. `marca : String = "Braun"`).
- **Mensaje**: instrucción enviada a un objeto para disparar su comportamiento; puede ser reflexivo (un objeto se envía un mensaje a sí mismo). Tipos de mensaje: constructores, destructores, selectores, modificadores, iteradores.
- **Responsabilidad**: contrato informal de lo que debe hacer una clase. **Restricción**: forma formal de eliminar ambigüedad, escrita entre llaves `{...}`, formalizable con **OCL** (Object Constraint Language, uno de los 4 documentos que especifican UML 2 junto con Diagram Interchange, UML Infrastructure y UML Superstructure — ver [[conceptos/uml]]).

## Representación de una clase
Rectángulo de **tres compartimentos**: (1) nombre de la clase (en negrita, centrado, en cursiva si es abstracta), (2) atributos, (3) operaciones `nombre(parámetros) : tipo_retorno`. Cualquier compartimento puede ocultarse sin que eso signifique que esté vacío.

### Visibilidad
| Símbolo | Nivel | Alcance |
|---|---|---|
| `+` | público | accesible desde cualquier clase |
| `#` | protegido | accesible desde la misma clase, amigas y clases derivadas |
| `-` | privado | accesible solo desde la misma clase (y amigas, en C++) |

Si se omite el especificador: los **atributos** se asumen privados y las **operaciones** públicas por defecto.

## Declaración de clase (pseudocódigo UPSAM)
```
clase NombreClase
  const
    [privado|público|protegido] tipo: nombre = valor
  var
    [estático][privado|público|protegido] tipo: nombre = [valor_inicial]
  constructor NombreClase(parámetros) ... fin_constructor
  [privado|público|protegido] tipo función nombre(parámetros) ... fin_función
  destructor NombreClase() ... fin_destructor
fin_clase
```
Equivale a `class` en C++/Java/C#. En C++, especificación e implementación suelen separarse (archivo `.h` + `.cpp`); en Java van juntas en la misma clase.

## Declaración y acceso a objetos
`NombreClase: identificador` declara la instancia (p. ej. `Punto: p`). En lenguajes con asignación dinámica (Java, C#), la declaración ocurre en dos etapas: declarar la variable y asignarle un objeto con `nuevo`/`new`, que reserva memoria en tiempo de ejecución y devuelve una referencia. El **operador punto** (`.`) accede a atributos/operaciones de un objeto: `p.fijarX(100)`.

La ocultación de información se implementa con los tres especificadores de acceso — ver el ciclo de vida del objeto (constructores/destructores) en [[conceptos/constructores-destructores]].

## Referencias
- [[fuentes/joyanes-aguilar-fundamentos-de-programacion]]
- [[conceptos/uml]]
- [[conceptos/programacion-orientada-a-objetos]]
- [[conceptos/constructores-destructores]]
