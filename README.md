# MRR-Top0: Topological PageRank for Augmented Retrieval

Classical information retrieval metrics such as Mean Reciprocal Rank (MRR)
evaluate only the position of the *first* relevant item, ignoring both
deeper relevant results and the structural quality of the retrieved set within
the corpus graph.  We introduce *MRR-Top0*, a novel ranking metric that
extends MRR to the entire top-$k$ result list by weighting each relevant
item's reciprocal rank with a *topology factor* $$T_{q,i}$$.  This factor
combines three graph signals computed on the corpus feature graph:
*Personalized PageRank* (random-walk affinity from the query anchor),
a *conductance penalty* (subgraph cohesion), and a *modularity gain*
(community alignment).  The resulting score evaluates both relevance order
and structural coherence in a single, bounded, label-agnostic quantity.
MRR-Top0 is applicable to any retrieval system operating over an
embedding space equipped with a graph Laplacian, including spectral
vector databases, RAG pipelines, and topology-aware search engines, and
provides a computationally cheap proxy for assessing whether a ranking
reflects the learned manifold structure of the dataset, not merely
geometric proximity.  We present the formal definition, explain every
constituent, discuss key properties and practical guidance, and situate
the metric within the broader landscape of graph-aware retrieval
