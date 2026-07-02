---
titulo: "Algoritmo de Leiden"
tipo: concepto
creado: 2026-07-01
actualizado: 2026-07-01
tags: [algoritmo-leiden, deteccion-de-comunidades, grafos, graphrag]
fuentes: []
---

# Algoritmo de Leiden

Algoritmo de **detección de comunidades** en grafos: agrupa nodos fuertemente conectados entre sí (y débilmente conectados con el resto) en "comunidades", de forma jerárquica — desde comunidades muy específicas hasta agrupaciones temáticas amplias. Es la técnica que [[conceptos/graph-rag]] aplica sobre el [[conceptos/grafo-de-conocimiento]] extraído de un corpus para generar resúmenes por comunidad antes de responder consultas — ver la fase de "Detección de Comunidades" en [[conceptos/graph-rag]].

## Por qué Leiden y no Louvain
Leiden (Traag, Waltman y van Eck, 2019) es una mejora sobre el algoritmo Louvain, más antiguo y también usado para detección de comunidades. El problema que corrige: Louvain puede producir comunidades **mal conectadas o incluso desconectadas internamente** como artefacto de su heurística de optimización local. Leiden garantiza que toda comunidad resultante esté **bien conectada**, mediante una fase adicional de refinamiento que Louvain no tiene.

## Cómo funciona (a alto nivel)
1. **Fase local**: mueve nodos individuales entre comunidades vecinas si eso mejora una métrica de calidad de partición (modularidad).
2. **Fase de refinamiento** (la que distingue a Leiden de Louvain): dentro de cada comunidad ya formada, vuelve a subdividir en sub-comunidades bien conectadas, evitando el problema de comunidades internamente fragmentadas.
3. **Agregación**: cada comunidad se colapsa en un único nodo y el proceso se repite sobre ese grafo reducido, produciendo niveles jerárquicos sucesivos.

## Uso en GraphRAG
[[conceptos/graph-rag]] aplica Leiden sobre el grafo de entidades extraído por un LLM del corpus de documentos. Cada comunidad resultante recibe un resumen generado por LLM de forma anticipada (antes de cualquier consulta), lo que permite responder preguntas globales de síntesis agregando resúmenes de comunidades relevantes en vez de recuperar chunks de texto individuales.

## Referencias
- [[conceptos/graph-rag]]
- [[conceptos/grafo-de-conocimiento]]
- [From Local to Global: A Graph RAG Approach (paper original)](https://arxiv.org/abs/2404.16130)
- [Traag, Waltman, van Eck. "From Louvain to Leiden" (2019)](https://arxiv.org/abs/1810.08473)
