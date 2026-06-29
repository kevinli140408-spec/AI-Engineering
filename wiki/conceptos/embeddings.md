---
titulo: "Embeddings (Representaciones Vectoriales)"
tipo: concepto
creado: 2026-06-29
actualizado: 2026-06-29
tags: [embeddings, vectores, semantica, nlp, rag]
fuentes: []
---

# Embeddings (Representaciones Vectoriales)

## Resumen

Un embedding es una representación numérica de texto (o cualquier dato) como un vector de números de punto flotante en un espacio de alta dimensión. La propiedad clave: **textos con significado similar quedan cerca en el espacio vectorial**. Esto permite búsqueda semántica, no solo búsqueda por palabras exactas.

Son el componente que hace posible el retrieval en [[conceptos/retrieval-augmented-generation]].

## Cómo Funcionan

Un modelo de embedding (ej. `text-embedding-3-small` de OpenAI, o modelos de Sentence Transformers) toma texto y produce un vector de cientos o miles de dimensiones:

```
"el gato come pescado"  →  [0.12, -0.45, 0.87, ..., 0.03]  (1536 dimensiones)
"un felino consume pez" →  [0.13, -0.44, 0.85, ..., 0.04]  (muy similares)
"política fiscal 2024"  →  [-0.72, 0.31, -0.12, ..., 0.91]  (muy diferente)
```

La similitud entre vectores se mide con **similitud coseno** o distancia euclidiana.

## Uso en RAG

1. En la fase de ingesta: cada chunk de documento se convierte a embedding y se almacena en la [[conceptos/base-de-datos-vectorial]]
2. En la fase de consulta: la query del usuario se convierte al mismo espacio vectorial
3. Se buscan los embeddings de chunks más cercanos al embedding de la query

Es crítico usar el **mismo modelo de embedding** para indexar y para consultar.

## Modelos Comunes

| Modelo | Dimensiones | Notas |
|---|---|---|
| `text-embedding-3-small` (OpenAI) | 1536 | Económico, buena calidad |
| `text-embedding-3-large` (OpenAI) | 3072 | Mayor calidad |
| `all-MiniLM-L6-v2` (Sentence Transformers) | 384 | Open source, rápido |
| `nomic-embed-text` | 768 | Open source, competitivo |

## Referencias

- [The Complete Guide to Embeddings and RAG](https://medium.com/@sharanharsoor/the-complete-guide-to-embeddings-and-rag-from-theory-to-production-758a16d747ac)
- [RAG Pipeline Deep Dive](https://dev.to/derrickryangiggs/rag-pipeline-deep-dive-ingestion-chunking-embedding-and-vector-search-2877)
