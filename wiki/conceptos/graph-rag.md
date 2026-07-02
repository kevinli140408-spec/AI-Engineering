---
titulo: "GraphRAG"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [graphrag, rag, knowledge-graph, microsoft, comunidades, razonamiento]
fuentes: []
---

# GraphRAG

## Resumen

GraphRAG es una variante de [[conceptos/retrieval-augmented-generation]] desarrollada por **Microsoft Research** (2024) que reemplaza la recuperación por similitud vectorial con un [[conceptos/grafo-de-conocimiento]]. En lugar de buscar chunks de texto parecidos a la query, navega un grafo de entidades y relaciones extraído del corpus, lo que permite responder preguntas que requieren razonamiento multi-salto y síntesis de información dispersa.

Resultados reportados por Microsoft: **80% de respuestas correctas vs 50% de RAG tradicional** en preguntas globales sobre un corpus.

## El Problema que Resuelve

El RAG vectorial falla en **preguntas globales**: aquellas que requieren sintetizar información de múltiples documentos o entender cómo se relacionan conceptos a lo largo de todo el corpus.

Ejemplo de query que RAG falla pero GraphRAG maneja bien:
> *"¿Cuáles son los temas principales que atraviesan todo este conjunto de documentos?"*
> *"¿Qué personajes están conectados con la organización X a lo largo del tiempo?"*

## Arquitectura: Tres Fases

### 1. Extracción (Indexación offline)
- Un LLM (GPT-4) lee todos los documentos y extrae **entidades** (personas, orgs, conceptos) y **relaciones** entre ellas
- Se construye el [[conceptos/grafo-de-conocimiento]]
- Las relaciones adicionales se infieren por co-ocurrencia semántica

### 2. Detección de Comunidades
- Se aplica el [[conceptos/algoritmo-leiden|algoritmo Leiden]] sobre el grafo para agrupar entidades fuertemente relacionadas en **comunidades**
- Las comunidades son jerárquicas: van de muy específicas (nivel bajo) a muy temáticas (nivel alto)
- Para cada comunidad, el LLM genera un **resumen** de manera anticipada (antes de cualquier query)

### 3. Consulta (dos modos)

| Modo | Descripción | Mejor para |
|---|---|---|
| **Global search** | Agrega resúmenes de comunidades relevantes para responder | Preguntas temáticas, síntesis de corpus |
| **Local search** | Combina vecindad del grafo + chunks de texto | Preguntas factuales específicas sobre entidades |

## Comparación con RAG Tradicional

| Dimensión | RAG vectorial | GraphRAG |
|---|---|---|
| Estructura de conocimiento | Chunks de texto | Grafo de entidades y relaciones |
| Recuperación | Similitud coseno (embeddings) | Navegación de grafo + resúmenes de comunidades |
| Preguntas locales (factual) | Bueno | Comparable |
| Preguntas globales (síntesis) | Pobre | Muy superior (+50-70% comprehensividad) |
| Costo de indexación | Bajo | Alto (LLM extrae entidades de todo el corpus) |
| Latencia de consulta | Baja | Variable (global search es costosa) |

## Variante: LazyGraphRAG

Para reducir el alto costo de indexación, **LazyGraphRAG** omite la construcción completa del grafo y los resúmenes anticipados. Construye el grafo de forma perezosa (solo cuando se necesita), manteniendo costos de indexación similares al RAG vectorial normal.

## Implementación Open Source

Microsoft publicó GraphRAG como proyecto open source en **julio 2024**, superando 20,000 estrellas en GitHub rápidamente. Disponible en: [github.com/microsoft/graphrag](https://github.com/microsoft/graphrag)

## Cuándo Usar GraphRAG vs RAG

**Usar GraphRAG cuando:**
- El corpus es grande y heterogéneo (muchos documentos relacionados)
- Las preguntas son temáticas, de síntesis, o requieren razonamiento multi-salto
- Importa entender relaciones entre entidades

**Usar RAG vectorial cuando:**
- Las preguntas son factuales y localizada en un fragmento específico
- El presupuesto de indexación es limitado
- La latencia es crítica

## Referencias

- [[conceptos/algoritmo-leiden]]
- [Microsoft Research: Project GraphRAG](https://www.microsoft.com/en-us/research/project/graphrag/)
- [Paper original: From Local to Global (arXiv 2404.16130)](https://arxiv.org/abs/2404.16130)
- [IBM: What is GraphRAG?](https://www.ibm.com/think/topics/graphrag)
- [RAG vs. GraphRAG: A Systematic Evaluation (arXiv 2502.11371)](https://arxiv.org/html/2502.11371v2)
- [DataCamp: GraphRAG Tutorial](https://www.datacamp.com/tutorial/graphrag)
