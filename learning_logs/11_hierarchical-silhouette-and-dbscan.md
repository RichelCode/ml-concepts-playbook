# 11 — Hierarchical Clustering, Silhouette, and DBSCAN

## Focus of this block

This block expands clustering beyond K-Means. It covers hierarchical clustering for cluster structure, silhouette score for validation, and DBSCAN for density-based grouping and explicit noise handling.

## Core concepts

### Hierarchical clustering

Hierarchical clustering builds a nested cluster structure rather than directly outputting only one flat partition.

Two main styles exist:

- **Agglomerative**: start with each point as its own cluster and merge upward
- **Divisive**: start with one large cluster and split downward

Agglomerative clustering is more common in introductory workflows.

### Linkage criteria

When merging clusters, the algorithm needs a definition of inter-cluster distance.

Common linkages:
- **single linkage**: nearest points
- **complete linkage**: farthest points
- **average linkage**: average pairwise distance
- **ward linkage**: merge clusters that minimally increase within-cluster variance

Choice of linkage changes the shape and behavior of the clustering process.

### Dendrogram

A dendrogram is the tree-like diagram that shows the merging process. It helps visualize cluster hierarchy and choose a cut level for the final number of clusters.

### Silhouette score

Silhouette score evaluates how well a point fits within its own cluster compared with other clusters.

Intuition:
- high silhouette → point is well matched to its own cluster and separated from others
- near zero → boundary point
- negative → possibly assigned to the wrong cluster

It is a helpful validation tool, especially for clustering methods like K-Means and hierarchical clustering.

### DBSCAN intuition

DBSCAN is density-based. Instead of assuming spherical clusters or requiring `K`, it groups points according to dense regions.

Key terms:
- **eps**: neighborhood radius
- **min_samples**: minimum points needed to form a dense region
- **core point**: enough nearby neighbors
- **border point**: near a core point but not dense enough itself
- **noise point**: does not belong to any dense cluster

### Why DBSCAN is powerful

- can find irregularly shaped clusters
- does not require choosing K beforehand
- naturally labels outliers as noise

### DBSCAN limitations

- sensitive to `eps` and `min_samples`
- can struggle when clusters have very different densities
- still benefits from scaling

### When to choose which clustering method

Use **K-Means** when:
- clusters are compact and roughly spherical
- K is known or can be estimated well

Use **Hierarchical Clustering** when:
- you want a cluster hierarchy or dendrogram
- interpretability of merge structure matters

Use **DBSCAN** when:
- cluster shape may be irregular
- noise detection matters
- choosing K is undesirable

## Interview-ready takeaways

- Hierarchical clustering gives structure; DBSCAN gives density-based grouping and noise handling.
- Silhouette score helps evaluate cluster separation and cohesion.
- DBSCAN can discover non-spherical clusters that K-Means may miss.
- Every clustering method encodes a different assumption about what a “cluster” looks like.

## Quick review questions

1. What does a dendrogram show?
2. Why can hierarchical clustering be useful even if K-Means is simpler?
3. What does silhouette score measure?
4. What are core, border, and noise points in DBSCAN?
5. Why is DBSCAN often better than K-Means for irregular cluster shapes?

## Keywords

`hierarchical clustering`, `agglomerative clustering`, `linkage`, `dendrogram`, `silhouette score`, `DBSCAN`, `core point`, `noise point`
