# Week 6 — RBD, Two-Way ANOVA, and Simple Linear Regression (Short Study Material)

## 1) Randomized Block Design (RBD)

RBD is used when experimental units are heterogeneous and a nuisance factor can be blocked.

- **Goal**: reduce unexplained error (MSE) by isolating block effects.
- **When useful**: CRD assumptions of homogeneous units are weak.

Model (one observation per treatment-block cell):

$$
Y_{ij}=\mu+\tau_i+\beta_j+\varepsilon_{ij}
$$

where $\tau_i$ = treatment effect, $\beta_j$ = block effect.

ANOVA decomposition:

$$
SS_T = SS_{\text{treat}} + SS_{\text{block}} + SS_E
$$

F-tests:

$$
F_{\text{treat}}=\frac{MS_{\text{treat}}}{MS_E},
\qquad
F_{\text{block}}=\frac{MS_{\text{block}}}{MS_E}
$$

---

## 2) Factorial Experiments / Two-Way ANOVA

Used to study two factors simultaneously and their interaction.

Model:

$$
Y_{ijk}=\mu+\alpha_i+\beta_j+(\alpha\beta)_{ij}+\varepsilon_{ijk}
$$

- $\alpha_i$: main effect of factor A
- $\beta_j$: main effect of factor B
- $(\alpha\beta)_{ij}$: interaction effect

Important idea:
- Parallel profile lines -> little/no interaction
- Non-parallel lines -> interaction likely

ANOVA components:

$$
SS_T = SS_A + SS_B + SS_{AB} + SS_E
$$

F ratios:

$$
F_A=\frac{MS_A}{MS_E},\quad
F_B=\frac{MS_B}{MS_E},\quad
F_{AB}=\frac{MS_{AB}}{MS_E}
$$

---

## 3) Simple Linear Regression (SLR)

Used to model relationship between one independent variable $X$ and dependent variable $Y$.

Population model:

$$
Y=\beta_0+\beta_1X+\varepsilon
$$

Estimated line:

$$
\hat{Y}=b_0+b_1X
$$

Interpretation:
- $b_1$: expected change in $Y$ for one-unit increase in $X$
- $b_0$: predicted $Y$ when $X=0$

---

## 4) Least Squares Estimation

Least squares minimizes:

$$
SSE=\sum (y_i-\hat{y}_i)^2
$$

Useful sums:

$$
S_{xx}=\sum (x_i-\bar{x})^2,
\quad
S_{yy}=\sum (y_i-\bar{y})^2,
\quad
S_{xy}=\sum (x_i-\bar{x})(y_i-\bar{y})
$$

Slope and intercept:

$$
b_1=\frac{S_{xy}}{S_{xx}},
\qquad
b_0=\bar{y}-b_1\bar{x}
$$

Best-fit line property:

$$
(\bar{x},\bar{y}) \text{ lies on } \hat{Y}=b_0+b_1X
$$

---

## 5) Goodness of Fit and Error Decomposition

Total variation split:

$$
SST=SSR+SSE
$$

where

$$
SST=\sum (y_i-\bar{y})^2,
\quad
SSR=\sum (\hat{y}_i-\bar{y})^2,
\quad
SSE=\sum (y_i-\hat{y}_i)^2
$$

Coefficient of determination:

$$
R^2=\frac{SSR}{SST}=1-\frac{SSE}{SST}
$$

$R^2$ = proportion of variability in $Y$ explained by regression on $X$.

---

## 6) Significance Tests in SLR

Common hypothesis:

$$
H_0:\beta_1=0
\qquad
\text{vs}
\qquad
H_a:\beta_1\ne 0
$$

t-test for slope:

$$
t=\frac{b_1}{SE(b_1)},\quad df=n-2
$$

ANOVA F-test:

$$
F=\frac{MSR}{MSE},\quad df=(1,\,n-2)
$$

In SLR, these are equivalent via $F=t^2$.

---

## 7) Quick Revision Points

- Use RBD when nuisance variability is large and can be blocked.
- Two-way ANOVA can test two main effects + interaction together.
- In SLR, least squares gives line minimizing squared residuals.
- $R^2$ quantifies explained variation, not causality.
