---
titulo: "Retrieval-Augmented Generation (RAG)"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [rag, llm, recuperacion, generacion, arquitectura]
fuentes: []
---

# Retrieval-Augmented Generation (RAG)

## Resumen

RAG es una arquitectura de IA que combina modelos de lenguaje (LLMs) con una base de conocimiento externa. Antes de generar una respuesta, el sistema **recupera** documentos relevantes y los inyecta como contexto en el prompt del modelo. Esto ancla las respuestas en datos reales y reduce las alucinaciones.

El problema que resuelve: los LLMs tienen conocimiento estático (hasta su fecha de corte) y no saben nada de documentos privados. RAG les da acceso a información actualizada y específica sin necesidad de re-entrenar el modelo.

## Arquitectura

Un sistema RAG tiene dos fases principales:

### Fase de Ingesta (offline)
1. **Carga de documentos** — se recolectan los documentos fuente (PDFs, páginas web, bases de datos)
2. **Chunking** — los documentos se dividen en fragmentos manejables (ver [[conceptos/chunking]])
3. **Embedding** — cada chunk se convierte en un vector numérico (ver [[conceptos/embeddings]])
4. **Almacenamiento** — los vectores se guardan en una [[conceptos/base-de-datos-vectorial]]

### Fase de Consulta (tiempo real)
1. **Query del usuario** — el usuario hace una pregunta
2. **Embed de la query** — la pregunta se convierte al mismo espacio vectorial
3. **Búsqueda por similitud** — se recuperan los top-K chunks más similares
4. **Augmentación del prompt** — los chunks se insertan como contexto en el prompt
5. **Generación** — el LLM produce la respuesta basándose en el contexto recuperado

## Componentes Clave

| Componente | Rol |
|---|---|
| **Retriever** | Busca documentos relevantes para la query |
| **Base vectorial** | Almacena embeddings; permite búsqueda semántica |
| **Generador (LLM)** | Produce la respuesta final usando el contexto |
| **Capa de orquestación** | Ensambla el prompt con contexto y query |

## Ventajas y Limitaciones

**Ventajas:**
- Acceso a conocimiento actualizado sin re-entrenar
- Respuestas verificables (se puede citar la fuente)
- Funciona con documentos privados/internos
- Menor costo que el fine-tuning

**Limitaciones:**
- La calidad depende de la calidad del retriever
- Si el chunk relevante no se recupera, la respuesta falla
- Latencia adicional por la fase de recuperación
- Chunking mal calibrado degrada el rendimiento

## Variantes

- **RAG Naive** — pipeline simple: recuperar → augmentar → generar
- **RAG Modular** — componentes independientes y optimizables por separado
- **[[conceptos/graph-rag|GraphRAG]]** — usa grafos de conocimiento en lugar de solo vectores
- **Agentic RAG** — el LLM decide cuándo y cómo recuperar (búsqueda iterativa)

## Referencias

- [RAG Architecture Explained](https://bigdataboutique.com/blog/rag-architecture-explained-how-retrieval-augmented-generation-works)
- [RAG Pipeline Deep Dive](https://dev.to/derrickryangiggs/rag-pipeline-deep-dive-ingestion-chunking-embedding-and-vector-search-2877)
- [IBM: Vector Databases for RAG](https://www.ibm.com/think/topics/rag-vector-database)
