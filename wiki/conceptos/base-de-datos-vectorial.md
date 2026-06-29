---
titulo: "Base de Datos Vectorial"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [vector-database, recuperacion, embeddings, rag, similitud]
fuentes: []
---

# Base de Datos Vectorial

## Resumen

Una base de datos vectorial almacena [[conceptos/embeddings]] y permite búsquedas eficientes por similitud semántica. Es el componente de almacenamiento y recuperación central de un sistema [[conceptos/retrieval-augmented-generation]].

A diferencia de bases de datos relacionales (que buscan por igualdad exacta), una base vectorial responde a: *"¿qué documentos son semánticamente más parecidos a esta query?"*

## Cómo Funciona

1. Se almacenan vectores (embeddings) junto con metadatos y el texto original del chunk
2. Cuando llega una query (ya convertida a vector), la BD calcula similitud contra todos los vectores almacenados
3. Devuelve los **top-K** vectores más cercanos (mayor similitud coseno)

Para escalar a millones de vectores, usan índices aproximados como **HNSW** (Hierarchical Navigable Small World) o **IVF** que sacrifican un poco de exactitud a cambio de velocidad.

## Herramientas Principales

| Herramienta | Tipo | Notas |
|---|---|---|
| **Pinecone** | Cloud managed | Fácil de usar, popular en producción |
| **Weaviate** | Open source / cloud | Soporte multimodal |
| **Qdrant** | Open source | Alto rendimiento, escrito en Rust |
| **Chroma** | Open source | Popular para prototipos y desarrollo local |
| **pgvector** | Extensión PostgreSQL | Ideal si ya se usa Postgres |
| **FAISS** | Librería (Meta) | Alta performance, no tiene servidor propio |
| **MongoDB Atlas** | Cloud managed | Vector search integrado en MongoDB |

## Componentes de un Registro

Cada entrada típicamente almacena:
- `id` — identificador único del chunk
- `vector` — el embedding (array de floats)
- `texto` — el contenido del chunk original
- `metadata` — fuente, fecha, sección, etc. (útil para filtrar)

## Relación con RAG

La base de datos vectorial es la "memoria no-paramétrica" del sistema RAG: guarda el conocimiento externo de forma que el retriever pueda acceder eficientemente. Sin ella, habría que pasar todos los documentos al contexto del LLM en cada query (inviable a escala).

## Referencias

- [IBM: Vector Databases for RAG](https://www.ibm.com/think/topics/rag-vector-database)
- [MongoDB RAG Docs](https://www.mongodb.com/docs/atlas/atlas-vector-search/rag/)
- [The Ultimate Guide to Vector DB and RAG Pipeline](https://learnopencv.com/vector-db-and-rag-pipeline-for-document-rag/)
