# Week 4 — Hypothesis Testing (Short Study Material)

## 1) Hypothesis Testing Basics

Hypothesis testing checks whether sample evidence is strong enough to reject a claim about a population parameter.

- **Null hypothesis**: $H_0$ (status quo / baseline claim)
- **Alternative hypothesis**: $H_a$ (what you want to test against $H_0$)
- Decision is based on test statistic, critical value, or p-value.

---

## 2) Types of Alternative Hypotheses

- **Left-tailed**: $H_a: \mu < \mu_0$
- **Right-tailed**: $H_a: \mu > \mu_0$
- **Two-tailed**: $H_a: \mu \ne \mu_0$

Significance level $\alpha$ defines rejection region size.

---

## 3) Type I and Type II Errors

- **Type I error**: Reject $H_0$ when $H_0$ is true
  - Probability: $\alpha$
- **Type II error**: Fail to reject $H_0$ when $H_0$ is false
  - Probability: $\beta$
- **Power of test**: $1-\beta$

Trade-off: lowering $\alpha$ can increase $\beta$ (for fixed sample size).

---

## 4) One-Sample Z Test for Mean ($\sigma$ known)

Use when population SD $\sigma$ is known.

$$
Z=\frac{\bar{X}-\mu_0}{\sigma/\sqrt{n}}
$$

Decision rules:
- p-value method: reject $H_0$ if $p\text{-value} \le \alpha$
- critical value method depends on tail type:

Left-tailed:

$$
\text{Reject }H_0 \text{ if } Z < -z_{\alpha}
$$

Right-tailed:

$$
\text{Reject }H_0 \text{ if } Z > z_{\alpha}
$$

Two-tailed:

$$
\text{Reject }H_0 \text{ if } |Z| > z_{\alpha/2}
$$

---

## 5) One-Sample t Test for Mean ($\sigma$ unknown)

Use when population SD is unknown (especially small samples from near-normal population).

$$
t=\frac{\bar{X}-\mu_0}{s/\sqrt{n}}, \qquad df=n-1
$$

Decision format is same as Z-test, replacing Z critical values with t critical values.

---

## 6) One-Sample Test for Proportion

For large samples, test population proportion $p$:

$$
Z=\frac{\hat{p}-p_0}{\sqrt{\frac{p_0(1-p_0)}{n}}}
$$

Typical adequacy check:

$$
np_0\ge5, \quad n(1-p_0)\ge5
$$

---

## 7) Two-Sample Mean Testing (Independent Samples)

Goal: test if two population means differ.

$$
H_0:\mu_1-\mu_2=\Delta_0
$$

Commonly $\Delta_0=0$.

If population variances are known:

$$
Z=\frac{(\bar{X}_1-\bar{X}_2)-\Delta_0}{\sqrt{\frac{\sigma_1^2}{n_1}+\frac{\sigma_2^2}{n_2}}}
$$

If variances unknown and assumed equal (pooled t-test):

$$
t=\frac{(\bar{X}_1-\bar{X}_2)-\Delta_0}{s_p\sqrt{\frac{1}{n_1}+\frac{1}{n_2}}},
\qquad
s_p^2=\frac{(n_1-1)s_1^2+(n_2-1)s_2^2}{n_1+n_2-2}
$$

with $df=n_1+n_2-2$.

---

## 8) Quick Revision Points

- First frame correct $H_0$ and $H_a$; that is the most important step.
- Choose test by what is known: $\sigma$ known -> Z, unknown -> t.
- Tail type comes from wording of the claim (less than, greater than, not equal).
- Always report p-value and practical conclusion in context.
