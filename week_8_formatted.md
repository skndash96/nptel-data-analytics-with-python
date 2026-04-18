# Week 8 — Maximum Likelihood and Logistic Regression (Short Study Material)

## 1) Maximum Likelihood Estimation (MLE)

MLE estimates unknown parameters by choosing values that make observed data most probable.

For independent observations $x_1,\dots,x_n$ with parameter $\theta$:

$$
L(\theta)=\prod_{i=1}^{n} f(x_i\mid\theta)
$$

Log-likelihood:

$$
\ell(\theta)=\log L(\theta)=\sum_{i=1}^{n}\log f(x_i\mid\theta)
$$

MLE condition (typically):

$$
\frac{\partial \ell(\theta)}{\partial \theta}=0
$$

Choose parameter value that maximizes $\ell(\theta)$.

---

## 2) MLE for Normal Distribution

If $X_i\sim N(\mu,\sigma^2)$:

$$
f(x)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)
$$

MLEs:

$$
\hat{\mu}_{MLE}=\bar{x}
$$

$$
\hat{\sigma}^2_{MLE}=\frac{1}{n}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

Note: MLE variance uses denominator $n$ (not $n-1$).

---

## 3) MLE in Regression Context

- Least squares and MLE are closely related when errors are normal.
- If normal-error assumptions are weak, MLE is often preferred/flexible.
- MLE framework works for many distributions (binomial, Poisson, exponential, etc.).

---

## 4) Why Logistic Regression?

Use logistic regression when dependent variable is binary (0/1, success/failure, yes/no).

- Linear regression is for continuous outcomes.
- Logistic regression models probability of class 1.

---

## 5) Logistic Regression Model

Let $p=P(Y=1\mid X)$.

### 5.1 Logistic (sigmoid) form

$$
p=\frac{1}{1+e^{-(\beta_0+\beta_1x_1+\cdots+\beta_kx_k)}}
$$

### 5.2 Logit form

$$
\log\left(\frac{p}{1-p}\right)=\beta_0+\beta_1x_1+\cdots+\beta_kx_k
$$

Here, $\frac{p}{1-p}$ is the **odds**.

---

## 6) Coefficient Interpretation in Logistic Regression

For predictor $x_j$:

$$
e^{\beta_j} = \text{odds ratio for 1-unit increase in }x_j
$$

- If $e^{\beta_j}>1$: odds increase
- If $e^{\beta_j}<1$: odds decrease

---

## 7) Significance Tests in Logistic Regression

### 7.1 Overall model significance (Likelihood ratio / G test)

$$
G=-2\log\left(\frac{L_0}{L_1}\right)=2\bigl[\ell(\text{full})-\ell(\text{reduced})\bigr]
$$

Under $H_0$, approximately:

$$
G\sim \chi^2_{df}
$$

### 7.2 Individual coefficient significance (Wald test)

For each coefficient:

$$
z=\frac{\hat{\beta}_j}{SE(\hat{\beta}_j)}
$$

Use p-value to decide significance.

---

## 8) Linear vs Logistic Regression (Core Differences)

- **Linear**: predicts continuous $Y$, model is linear in output scale.
- **Logistic**: predicts binary $Y$, model is linear in log-odds scale.
- **Range of prediction**:
  - Linear: $(-\infty,\infty)$
  - Logistic probability: $[0,1]$

---

## 9) Quick Revision Points

- MLE maximizes data likelihood under chosen distribution.
- Logistic regression is the standard model for binary classification.
- Use likelihood ratio test for overall model and Wald test for individual predictors.
- Interpret logistic coefficients using odds ratios, not direct probability changes.
