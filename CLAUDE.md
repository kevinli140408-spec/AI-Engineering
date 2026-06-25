# LLM Wiki — Esquema de Operación

Este vault de Obsidian es una **wiki personal de conocimiento** mantenida por un LLM.
El humano aporta fuentes, dirige el análisis y hace preguntas.
El LLM escribe, actualiza y mantiene toda la wiki.

Idioma: **español latinoamericano** para todo el contenido generado.

---

## Estructura de carpetas

```
raw/              ← Fuentes crudas (inmutables, el LLM nunca las modifica)
  assets/         ← Imágenes descargadas localmente
wiki/             ← Páginas generadas por el LLM (el humano solo lee)
  fuentes/        ← Resúmenes de cada fuente ingresada
  entidades/      ← Páginas de personas, herramientas, organizaciones, etc.
  conceptos/      ← Páginas de ideas, métodos, teorías, marcos teóricos
  analisis/       ← Comparaciones, síntesis, respuestas a preguntas complejas
index.md          ← Catálogo de todas las páginas del wiki
log.md            ← Registro cronológico de operaciones
CLAUDE.md         ← Este archivo (esquema)
```

---

## Convenciones de páginas

### Nombres de archivo
- Minúsculas, palabras separadas por guiones: `aprendizaje-espaciado.md`
- Sin acentos ni caracteres especiales en el nombre de archivo
- El título legible va dentro del frontmatter

### Frontmatter YAML (obligatorio en toda página wiki)
```yaml
---
titulo: "Título Legible"
tipo: fuente | entidad | concepto | analisis
creado: YYYY-MM-DD
actualizado: YYYY-MM-DD
tags: [tag1, tag2]
fuentes: [nombre-de-fuente]   # solo para entidades/conceptos/análisis
---
```

### Contenido
- Usar `[[enlaces wiki]]` para conectar páginas entre sí
- Citar fuentes con `[[fuentes/nombre]]`
- Incluir sección `## Referencias` al final si la página cita múltiples fuentes
- Máximo ~500 palabras por página; si crece más, dividir en sub-páginas

---

## Operaciones

### 1. Ingest (Ingesta de fuente)

Cuando el humano proporciona una nueva fuente:

1. **Leer** la fuente completa
2. **Discutir** los puntos clave con el humano (2-3 puntos, breve)
3. **Crear** página de resumen en `wiki/fuentes/`
4. **Actualizar** páginas existentes de entidades y conceptos que la fuente menciona
5. **Crear** nuevas páginas de entidades/conceptos si aparecen por primera vez
6. **Actualizar** `index.md` con las páginas nuevas/modificadas
7. **Agregar** entrada al `log.md`

### 2. Query (Consulta)

Cuando el humano hace una pregunta:

1. **Leer** `index.md` para identificar páginas relevantes
2. **Leer** las páginas relevantes
3. **Responder** con citas a páginas wiki `[[página]]`
4. Si la respuesta es valiosa, **guardarla** como página en `wiki/analisis/`
5. **Actualizar** `index.md` y `log.md` si se creó nueva página

### 3. Lint (Mantenimiento)

Bajo petición o periódicamente:

- Buscar contradicciones entre páginas
- Identificar páginas huérfanas (sin enlaces entrantes)
- Detectar conceptos mencionados pero sin página propia
- Verificar que `index.md` esté completo y actualizado
- Sugerir fuentes o preguntas para llenar vacíos

---

## Formato de index.md

```markdown
# Índice del Wiki

## Fuentes
- [[fuentes/nombre]] — Resumen de una línea (YYYY-MM-DD)

## Entidades
- [[entidades/nombre]] — Descripción breve

## Conceptos
- [[conceptos/nombre]] — Descripción breve

## Análisis
- [[analisis/nombre]] — Descripción breve
```

---

## Formato de log.md

Cada entrada sigue este formato para ser parseable:

```markdown
## [YYYY-MM-DD] tipo | Título
Descripción breve de lo que se hizo.
Páginas tocadas: [[pág1]], [[pág2]], ...
```

Tipos válidos: `ingesta`, `consulta`, `lint`, `actualización`

---

## Reglas generales

1. **Nunca modificar** archivos en `raw/` — son fuentes inmutables
2. **Siempre actualizar** `index.md` y `log.md` después de cualquier cambio al wiki
3. **Mantener enlaces** — si mencionas una entidad o concepto, enlázalo con `[[]]`
4. **Ser conciso** — resúmenes densos, no prosa inflada
5. **Señalar contradicciones** — si una fuente nueva contradice información existente, anotarlo explícitamente
6. **Fechas absolutas** — nunca usar "ayer" o "la semana pasada"; siempre YYYY-MM-DD
7. **Preguntar antes de asumir** — si no queda claro qué enfatizar, preguntar al humano
