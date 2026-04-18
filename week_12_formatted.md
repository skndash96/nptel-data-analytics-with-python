# Week 12 — Hierarchical Clustering and CART (Short Study Material)

## 1) Agglomerative Hierarchical Clustering (HAC)

HAC process:
1. compute pairwise distance matrix
2. start with each object as its own cluster
3. merge closest clusters iteratively
4. stop when one cluster remains (or earlier by rule)

Common base distance (for points):

$$
d(i,j)=\sqrt{\sum_{f=1}^{p}(x_{if}-x_{jf})^2}
$$

Output is summarized by a **dendrogram**.

---

## 2) CART: Classification and Regression Trees

CART is a tree-based predictive model.

- **Classification tree**: target is categorical
- **Regression tree**: target is continuous

Node splitting selects the attribute producing the “best” class separation.

---

## 3) Entropy and Information Gain

For dataset $D$ with class proportions $p_1,\dots,p_C$:

$$
Info(D)= -\sum_{i=1}^{C} p_i\log_2 p_i
$$

After splitting on attribute $A$ into partitions $D_1,\dots,D_v$:

$$
Info_A(D)=\sum_{j=1}^{v}\frac{|D_j|}{|D|}Info(D_j)
$$

Information gain:

$$
Gain(A)=Info(D)-Info_A(D)
$$

Higher gain -> better split (but may bias toward many-valued attributes).

---

## 4) Gain Ratio

To reduce information-gain bias, use split information:

$$
SplitInfo_A(D)= -\sum_{j=1}^{v}\frac{|D_j|}{|D|}\log_2\frac{|D_j|}{|D|}
$$

Gain ratio:

$$
GainRatio(A)=\frac{Gain(A)}{SplitInfo_A(D)}
$$

Prefer attributes with high gain ratio.

---

## 5) Gini Index (CART-style)

Impurity of dataset $D$:

$$
Gini(D)=1-\sum_{i=1}^{C}p_i^2
$$

After splitting by attribute $A$:

$$
Gini_A(D)=\sum_{j=1}^{v}\frac{|D_j|}{|D|}Gini(D_j)
$$

Choose split with lower post-split impurity (or larger impurity reduction).

---

## 6) CART Model Building Flow

1. choose split criterion (information gain / gain ratio / gini)
2. split node using best attribute
3. recurse on child nodes
4. stop by rules (pure node, min samples, max depth, etc.)
5. optionally prune to reduce overfitting

---

## 7) Python Workflow (as shown in lectures)

- encode categorical variables numerically (label encoding/one-hot as needed)
- fit tree model on training data
- visualize/interpret decision rules
- evaluate with validation/test data

---

## 8) Quick Revision Points

- HAC provides hierarchical grouping and dendrogram interpretation.
- CART builds interpretable if-then rules via recursive splits.
- Information gain, gain ratio, and gini are key attribute-selection metrics.
- Proper encoding and pruning are crucial for reliable tree models.
