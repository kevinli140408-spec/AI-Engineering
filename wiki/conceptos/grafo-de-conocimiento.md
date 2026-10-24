---
titulo: "Grafo de Conocimiento (Knowledge Graph)"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-10-24
tags: [knowledge-graph, grafos, entidades, relaciones, rag]
fuentes: []
---

# Grafo de Conocimiento (Knowledge Graph)

## Resumen

Un grafo de conocimiento es una estructura de datos que representa entidades del mundo real como **nodos** y las relaciones entre ellas como **aristas**. Es la base del [[conceptos/graph-rag]]: en lugar de almacenar texto plano en chunks, almacena conocimiento estructurado como una red de conexiones.

Ejemplo:
```
[Microsoft] --fundó--> [GraphRAG]
[GraphRAG]  --usa-->   [Algoritmo Leiden]
[GraphRAG]  --es variante de--> [RAG]
```

## Componentes

- **Nodos (entidades):** personas, organizaciones, lugares, conceptos, eventos
- **Aristas (relaciones):** verbos que conectan dos entidades (fundó, trabaja-en, es-parte-de, contradice)
- **Atributos:** propiedades de cada nodo o arista (fecha, descripción, peso de confianza)

## Construcción desde Texto

En el contexto de GraphRAG, el grafo se construye automáticamente:
1. Un LLM (ej. GPT-4) lee los documentos fuente
2. Extrae entidades nombradas y las relaciones entre ellas
3. Las relaciones adicionales se infieren por co-ocurrencia y similitud semántica
4. Se detectan comunidades de entidades relacionadas ([[conceptos/algoritmo-leiden|algoritmo Leiden]])

## Ventaja sobre Chunks de Texto

Un chunk de texto captura el contexto local de un párrafo. Un grafo captura conexiones a lo largo de **todo el corpus**: si la entidad A aparece en el documento 1 y en el documento 50 con relaciones distintas, el grafo conecta esos fragmentos de conocimiento que nunca coexistirían en el mismo chunk.

## Usos Más Allá de RAG

- Motores de recomendación (ej. grafos de usuario-producto)
- Detección de fraude (patrones de relaciones anómalas)
- Buscadores semánticos empresariales
- Sistemas de preguntas y respuestas sobre bases de conocimiento (Wikidata, Freebase)

## Referencias

- [[conceptos/graph-rag]]
- [[conceptos/algoritmo-leiden]]
- [IBM: What is GraphRAG?](https://www.ibm.com/think/topics/graphrag)
- [From Local to Global: A Graph RAG Approach (paper original)](https://arxiv.org/abs/2404.16130)
