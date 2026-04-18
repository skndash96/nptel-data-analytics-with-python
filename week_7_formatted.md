# Week 7 — Regression Intervals, Diagnostics, Multiple Regression, Categorical Predictors (Short Study Material)

## 1) Interval Estimation in Simple Regression

After fitting:

$$
\hat{Y}=b_0+b_1X
$$

at a specific predictor value $x_0$:

$$
\hat{y}_0=b_0+b_1x_0
$$

Residual standard error:

$$
s_e=\sqrt{\frac{SSE}{n-2}}
$$

---

## 2) Confidence Interval for Mean Response $E(Y\mid x_0)$

$$
\hat{y}_0 \pm t_{\alpha/2,\,n-2}\, s_e\sqrt{\frac{1}{n}+\frac{(x_0-\bar{x})^2}{S_{xx}}}
$$

Used when estimating the **average** response at $x_0$.

---

## 3) Prediction Interval for Individual Response at $x_0$

$$
\hat{y}_0 \pm t_{\alpha/2,\,n-2}\, s_e\sqrt{1+\frac{1}{n}+\frac{(x_0-\bar{x})^2}{S_{xx}}}
$$

Prediction interval is always wider than confidence interval for mean response.

---

## 4) Residual Analysis and Regression Assumptions

Residual for observation $i$:

$$
e_i=y_i-\hat{y}_i
$$

Core assumptions on error term $\varepsilon$:

$$
E(\varepsilon)=0
$$

$$
Var(\varepsilon)=\sigma^2 \;\text{(constant)}
$$

- errors are independent
- errors are approximately normal

Why important: validity of t-tests, F-tests, CIs, and prediction intervals.

Typical diagnostic plots:
- residuals vs fitted (linearity/constant variance)
- residuals vs order (independence)
- normal probability plot / histogram (normality)

---

## 5) Multiple Linear Regression (MLR)

When more than one independent variable is used:

$$
Y=\beta_0+\beta_1X_1+\beta_2X_2+\cdots+\beta_pX_p+\varepsilon
$$

Estimated model:

$$
\hat{Y}=b_0+b_1X_1+b_2X_2+\cdots+b_pX_p
$$

Each $b_j$ is a partial effect (holding other predictors fixed).

---

## 6) Goodness of Fit in MLR

Coefficient of determination:

$$
R^2=1-\frac{SSE}{SST}
$$

Adjusted $R^2$ (penalizes extra predictors):

$$
\bar{R}^2 = 1 - \frac{SSE/(n-p-1)}{SST/(n-1)}
$$

Use adjusted $R^2$ for fair model comparison with different numbers of predictors.

---

## 7) Significance Testing in MLR

### 7.1 Overall model significance (F-test)

$$
H_0:\beta_1=\beta_2=\cdots=\beta_p=0
$$

$$
H_a:\text{At least one }\beta_j\ne 0
$$

$$
F=\frac{MSR}{MSE}
$$

### 7.2 Individual predictor significance (t-test)

For each predictor $j$:

$$
H_0:\beta_j=0
\qquad
H_a:\beta_j\ne 0
$$

$$
t=\frac{b_j}{SE(b_j)},\quad df=n-p-1
$$

---

## 8) Categorical Predictors (Dummy Variables)

Categorical variables are encoded using 0/1 indicator variables.

For two-level category (e.g., gender):

$$
D=\begin{cases}
1, & \text{category present}\\
0, & \text{reference category}
\end{cases}
$$

Model with one numeric predictor $X$ and one dummy $D$:

$$
Y=\beta_0+\beta_1X+\beta_2D+\varepsilon
$$

- $\beta_2$ shifts intercept relative to reference category.
- With interactions (if added), slopes can differ by category.

---

## 9) Quick Revision Points

- CI estimates mean response; PI predicts a single new observation.
- Always validate assumptions using residual diagnostics.
- In MLR, use F-test for overall fit and t-tests for individual predictors.
- Use dummy coding to include categorical inputs in regression.
