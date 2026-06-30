---
titulo: "Chunking (Fragmentación de Documentos)"
tipo: concepto
creado: 2026-06-30
actualizado: 2026-06-30
tags: [chunking, rag, preprocesamiento, nlp]
fuentes: []
---

# Chunking (Fragmentación de Documentos)

## Resumen

Chunking es el proceso de dividir documentos largos en fragmentos ("chunks") más pequeños y manejables antes de convertirlos en [[conceptos/embeddings]]. Es el primer paso de la fase de ingesta en [[conceptos/retrieval-augmented-generation]]: un documento completo casi nunca se indexa de una sola vez, porque (a) los modelos de embedding tienen un límite de tokens de entrada, y (b) fragmentos más chicos producen vectores más específicos, lo que mejora la precisión de la búsqueda por similitud.

## Por Qué Importa

El tamaño y la calidad del chunking afectan directamente el rendimiento del sistema RAG completo:

- **Chunks muy grandes** → el embedding resultante mezcla demasiados temas, diluyendo la señal semántica; el retriever recupera contexto "ruidoso".
- **Chunks muy chicos** → se pierde contexto necesario para entender el fragmento de forma aislada (ej. una oración sin el párrafo que la rodea).
- Un chunk mal calibrado puede hacer que la respuesta del LLM falle aunque la información exista en la base de conocimiento — el [[conceptos/retrieval-augmented-generation|RAG]] solo es tan bueno como los chunks que recupera.

## Estrategias Comunes

| Estrategia | Descripción |
|---|---|
| **Fixed-size chunking** | Divide por cantidad fija de caracteres o tokens (ej. 500 tokens), con frecuencia agregando **overlap** (solapamiento) entre chunks consecutivos para no cortar ideas a la mitad |
| **Recursive character splitting** | Intenta cortar primero en límites "naturales" (párrafos, oraciones) y solo recurre al corte fijo si el fragmento sigue siendo muy grande |
| **Semantic chunking** | Agrupa oraciones según similitud semántica entre embeddings, en vez de por longitud |
| **Document-structure-aware** | Usa la estructura del documento (encabezados, secciones, tablas) como límites naturales de corte |

## Relación con Otros Componentes

1. **Carga de documentos** → **Chunking** → [[conceptos/embeddings|Embedding]] → almacenamiento en [[conceptos/base-de-datos-vectorial]]
2. El tamaño de chunk elegido debe ser compatible con el límite de contexto del modelo de embedding usado.
3. En [[conceptos/graph-rag|GraphRAG]], el chunking también alimenta la extracción de entidades y relaciones para construir el [[conceptos/grafo-de-conocimiento]].

## Referencias

- [RAG Pipeline Deep Dive](https://dev.to/derrickryangiggs/rag-pipeline-deep-dive-ingestion-chunking-embedding-and-vector-search-2877)
- [[conceptos/retrieval-augmented-generation]]
