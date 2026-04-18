# Week 10 — Chi-Square Tests and Cluster Analysis Introduction (Short Study Material)

## 1) Chi-Square Test: When to Use

Use chi-square methods for **categorical data** (nominal/ordinal), especially frequency tables.

Two major applications:
- test of independence (association between two categorical variables)
- goodness-of-fit (whether data follow a specified distribution)

---

## 2) Chi-Square Test of Independence

For an $r\times c$ contingency table:

Hypotheses:

$$
H_0:\text{variables are independent}
$$

$$
H_a:\text{variables are associated (not independent)}
$$

Expected count for cell $(i,j)$:

$$
E_{ij}=\frac{(\text{row total}_i)(\text{column total}_j)}{N}
$$

Test statistic:

$$
\chi^2=\sum_{i=1}^{r}\sum_{j=1}^{c}\frac{(O_{ij}-E_{ij})^2}{E_{ij}}
$$

Degrees of freedom:

$$
df=(r-1)(c-1)
$$

Decision: reject $H_0$ if p-value $\le \alpha$.

---

## 3) Chi-Square Goodness-of-Fit (GOF)

Used to test whether observed frequencies follow a target distribution (Poisson, uniform, normal, etc.).

Hypotheses:

$$
H_0:\text{data follow specified distribution}
$$

$$
H_a:\text{data do not follow specified distribution}
$$

Statistic:

$$
\chi^2=\sum_{k=1}^{m}\frac{(O_k-E_k)^2}{E_k}
$$

where $O_k$ = observed frequency, $E_k$ = expected frequency from target model.

Typical degrees of freedom:

$$
df=m-1-p
$$

with $m$ classes and $p$ estimated distribution parameters.

---

## 4) GOF for Common Distributions

- **Poisson**: estimate $\lambda$ using sample mean, then compute expected class probabilities.
- **Uniform**: equal expected probabilities across intervals.
- **Normal**: estimate $\mu,\sigma$, then expected counts from normal CDF over bins.

General expected count:

$$
E_k=N\cdot P(\text{class }k)
$$

---

## 5) Cluster Analysis: Core Idea

Cluster analysis groups objects so that:
- within-cluster similarity is high
- between-cluster similarity is low

It is mostly an **exploratory/descriptive** data-mining technique.

---

## 6) Data Types and Distance in Clustering

Choice of algorithm/distance depends on variable type (interval, ordinal, nominal, etc.).

Common distance metrics:

### 6.1 Euclidean distance

$$
d(i,j)=\sqrt{\sum_{f=1}^{p}(x_{if}-x_{jf})^2}
$$

### 6.2 Manhattan distance

$$
d(i,j)=\sum_{f=1}^{p}|x_{if}-x_{jf}|
$$

### 6.3 Minkowski distance

$$
d(i,j)=\left(\sum_{f=1}^{p}|x_{if}-x_{jf}|^q\right)^{1/q}
$$

Special cases: $q=1$ (Manhattan), $q=2$ (Euclidean).

---

## 7) Standardization in Clustering

When variables are on different scales, standardization is often needed to avoid dominance by large-scale variables.

z-score standardization:

$$
z_{if}=\frac{x_{if}-\bar{x}_f}{s_f}
$$

But standardization can alter apparent cluster structure; always validate interpretation.

---

## 8) Quick Revision Points

- Use chi-square for categorical-frequency analysis.
- Independence test needs contingency table and expected counts.
- GOF compares observed counts to model-based expected counts.
- Clustering quality depends strongly on variable scaling and distance choice.
