# Week 5 — Two-Sample Tests, Sample Size, ANOVA, Post Hoc (Short Study Material)

## 1) Two-Sample t Test (Unequal Variances: Welch t-test)

Use when:
- two independent random samples
- populations approximately normal
- population variances unknown and **not assumed equal**

Hypothesis (common form):

$$
H_0:\mu_1-\mu_2=\Delta_0 \quad (\text{often }\Delta_0=0)
$$

Test statistic:

$$
t=\frac{(\bar{X}_1-\bar{X}_2)-\Delta_0}{\sqrt{\frac{s_1^2}{n_1}+\frac{s_2^2}{n_2}}}
$$

Welch–Satterthwaite degrees of freedom:

$$
\nu=\frac{\left(\frac{s_1^2}{n_1}+\frac{s_2^2}{n_2}\right)^2}{\frac{\left(\frac{s_1^2}{n_1}\right)^2}{n_1-1}+\frac{\left(\frac{s_2^2}{n_2}\right)^2}{n_2-1}}
$$

---

## 2) Test for Two Population Variances (F-test)

Used to compare variances of two normal populations.

If testing $H_0:\sigma_1^2=\sigma_2^2$, use:

$$
F=\frac{s_1^2}{s_2^2}
$$

Distribution under $H_0$:

$$
F \sim F_{(n_1-1,\,n_2-1)}
$$

Tail (left/right/two) depends on $H_a$.

---

## 3) When to Use Z-test vs t-test

- **Z-test for mean**: population SD $\sigma$ known
- **t-test for mean**: population SD unknown (especially small $n$)
- As $n$ grows, t distribution approaches normal.

---

## 4) Sample Size Determination

### 4.1 For estimating population mean $\mu$

With tolerable error (margin) $E$ and known $\sigma$:

$$
n=\left(\frac{z_{\alpha/2}\sigma}{E}\right)^2
$$

If $\sigma$ is unknown, practical approximation:

$$
\sigma \approx \frac{\text{Range}}{4}
$$

### 4.2 For estimating population proportion $p$

$$
n=\frac{z_{\alpha/2}^2\,p(1-p)}{E^2}
$$

If no prior estimate of $p$, use $p=0.5$ (gives maximum required sample size).

---

## 5) One-Way ANOVA

Purpose: test equality of $k$ population means.

Hypotheses:

$$
H_0:\mu_1=\mu_2=\cdots=\mu_k
$$

$$
H_a:\text{At least one mean differs}
$$

ANOVA decomposition:

$$
SS_T = SS_B + SS_W
$$

- $SS_T$: total sum of squares
- $SS_B$: between-group sum of squares
- $SS_W$: within-group sum of squares

Mean squares and F-statistic:

$$
MS_B=\frac{SS_B}{k-1}, \qquad MS_W=\frac{SS_W}{N-k}
$$

$$
F=\frac{MS_B}{MS_W}
$$

Decision: reject $H_0$ if p-value $\le \alpha$.

---

## 6) Post Hoc Analysis After ANOVA

If ANOVA rejects $H_0$, identify which means differ.

Common methods:
- **Tukey / Tukey-Kramer**: pairwise comparisons with family-wise error control
- **LSD (Least Significant Difference)**: pairwise tests (less conservative)

Interpretation: ANOVA says "some difference exists"; post hoc says "which pairs differ."

---

## 7) Python Pointers (from class demos)

- One-way ANOVA in SciPy:

```python
from scipy import stats
stats.f_oneway(group1, group2, group3)
```

- Data reshaping for ANOVA workflows in pandas:

```python
pd.melt(...)
```

---

## 8) Quick Revision Points

- For two means with unequal variances, use Welch t-test.
- For variance comparison, use F-test (normality assumption matters).
- Better precision (smaller $E$) requires larger sample size.
- ANOVA first, then post hoc if ANOVA is significant.
