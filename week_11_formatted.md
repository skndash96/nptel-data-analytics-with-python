# Week 11 — Clustering Data Handling, K-Means, and Hierarchical Methods (Short Study Material)

## 1) Handling Missing Values in Clustering

Missing entries are common in real data matrices.

Key handling rules:
- remove objects with all values missing
- remove variables with all values missing
- compute summary statistics using available values only

For variable $f$ with available count $n_f$:

$$
\bar{x}_f=\frac{1}{n_f}\sum x_{if}
$$

Distance calculations should ignore unavailable components or use proper imputation.

---

## 2) Similarity and Dissimilarity Matrices

Clustering typically starts from pairwise dissimilarities.

Dissimilarity matrix $D=[d(i,j)]$:
- $d(i,i)=0$
- $d(i,j)=d(j,i)$ for symmetric measures

Similarity can be converted to dissimilarity and vice versa depending on algorithm.

---

## 3) Variable-Type-Specific Dissimilarity

### 3.1 Binary variables

Simple matching dissimilarity:

$$
d(i,j)=\frac{p-m}{p}
$$

where $p$ = number of binary attributes, $m$ = number of matches.

### 3.2 Categorical variables

Treat category equality as match/non-match; aggregate across attributes.

### 3.3 Ordinal variables

Convert ranks to $[0,1]$ scale:

$$
z_{if}=\frac{r_{if}-1}{M_f-1}
$$

then use numeric distance (e.g., Euclidean/Manhattan).

### 3.4 Interval and ratio variables

For interval, often normalize by range:

$$
d^{(f)}_{ij}=\frac{|x_{if}-x_{jf}|}{\max_h x_{hf}-\min_h x_{hf}}
$$

For ratio-scaled variables, log-transform is often used before scaling.

### 3.5 Mixed data

Compute per-variable normalized dissimilarity and aggregate across variable types.

---

## 4) K-Means Clustering (Partitioning)

Used when desired number of clusters $K$ is known.

Objective (within-cluster sum of squares):

$$
\min \sum_{k=1}^{K}\sum_{x_i\in C_k}\|x_i-\mu_k\|^2
$$

Algorithm steps:
1. initialize $K$ centroids
2. assign each point to nearest centroid
3. recompute centroids
4. repeat until convergence

Centroid update:

$$
\mu_k=\frac{1}{|C_k|}\sum_{x_i\in C_k}x_i
$$

---

## 5) Hierarchical Clustering

Builds a hierarchy (tree/dendrogram) of clusters.

Types:
- **Agglomerative** (bottom-up): start with singletons, merge closest clusters
- **Divisive** (top-down): start with one cluster, split recursively

Important note: once a merge/split is made, it is generally not undone.

---

## 6) Partitioning vs Hierarchical (When to Choose)

- K-means: faster for large numeric datasets; requires preset $K$.
- Hierarchical: useful when $K$ unknown and for dendrogram-based interpretation.
- In practice, try multiple methods and compare cluster quality/interpretability.

---

## 7) Quick Revision Points

- Good clustering depends on preprocessing (missing values + scaling + variable type handling).
- Use K-means for compact spherical-like numeric clusters.
- Use hierarchical methods for exploratory structure and cluster granularity.
