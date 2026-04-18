# Week 3 — Python Distribution Demo, Sampling, and Confidence Intervals (Short Study Material)

## 1) Python for Probability Distributions

Typical workflow in Python (`scipy.stats`):

- **Binomial PMF**: `binom.pmf(k, n, p)` gives $P(X=k)$
- **Binomial CDF**: `binom.cdf(k, n, p)` gives $P(X\le k)$
- Similar functions exist for Poisson, Normal, etc.

Example interpretation (binomial setting):

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

---

## 2) Population, Sample, and Statistical Inference

- **Population**: complete set of all items of interest.
- **Sample**: subset drawn from population.
- **Descriptive statistics**: summarize observed data.
- **Inferential statistics**: use sample to conclude about population.

Why sampling?
- less time
- lower cost
- practical when census is impossible

---

## 3) Sampling Distribution Essentials

A **sampling distribution** is the distribution of a statistic over repeated samples.

### 3.1 Sample Mean

If sample size is $n$ and population has mean $\mu$ and standard deviation $\sigma$:

$$
E(\bar{X})=\mu
$$

$$
\sigma_{\bar{X}}=\frac{\sigma}{\sqrt{n}}
$$

### 3.2 Sample Proportion

If population proportion is $p$:

$$
E(\hat{p})=p
$$

$$
\sigma_{\hat{p}}=\sqrt{\frac{p(1-p)}{n}}
$$

### 3.3 Sample Variance

For normal populations, inference on variance uses chi-square distribution.

---

## 4) Central Limit Theorem (CLT)

For sufficiently large $n$, sampling distribution of $\bar{X}$ is approximately normal, regardless of population shape.

$$
\bar{X} \approx N\left(\mu,\frac{\sigma^2}{n}\right)
$$

Key impact: enables normal-based inference for means.

---

## 5) Estimator vs Estimate

- **Estimator**: random variable/rule used to estimate parameter (e.g., $\bar{X}, S^2, \hat{p}$)
- **Estimate**: numerical value obtained from a sample

---

## 6) Confidence Interval (CI) Basics

General CI form:

$$
\text{Point Estimate} \pm \text{Margin of Error}
$$

Margin of error depends on confidence level and standard error.

---

## 7) CI for Population Mean $\mu$

### 7.1 When population variance $\sigma^2$ is known (Z-interval)

$$
\bar{x} \pm z_{\alpha/2}\frac{\sigma}{\sqrt{n}}
$$

Equivalent inequality form:

$$
\bar{x} - z_{\alpha/2}\frac{\sigma}{\sqrt{n}} \le \mu \le \bar{x} + z_{\alpha/2}\frac{\sigma}{\sqrt{n}}
$$

### 7.2 When population variance $\sigma^2$ is unknown (t-interval)

Use Student's t with degrees of freedom $n-1$.

Test statistic:

$$
t=\frac{\bar{X}-\mu}{S/\sqrt{n}}, \qquad df=n-1
$$

Confidence interval:

$$
\bar{x} \pm t_{\alpha/2,\,n-1}\frac{s}{\sqrt{n}}
$$

Use especially for smaller samples with approximately normal population.

---

## 8) CI for Population Proportion $p$

For large samples:

$$
\hat{p} \pm z_{\alpha/2}\sqrt{\frac{\hat{p}(1-\hat{p})}{n}}
$$

---

## 9) CI for Population Variance $\sigma^2$ (Normal Population)

Using chi-square distribution with $df=n-1$:

$$
\frac{(n-1)s^2}{\chi^2_{\alpha/2,\,n-1}} \le \sigma^2 \le \frac{(n-1)s^2}{\chi^2_{1-\alpha/2,\,n-1}}
$$

For standard deviation, take square roots of both limits.

---

## 10) Quick Revision Points

- Sampling distribution is the bridge from sample to population.
- CLT justifies normal approximation for sample means.
- Use Z-interval when $\sigma$ is known; use t-interval when $\sigma$ is unknown.
- Larger $n$ reduces standard error and narrows CI.
- Higher confidence level gives wider interval.
