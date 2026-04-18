# Week 2 — Probability and Probability Distributions (Short Study Material)

## 1) Probability Basics

Probability is the numerical likelihood that an event occurs.

$$
0 \le P(A) \le 1
$$

$$
P(S)=1, \qquad P(\varnothing)=0
$$

For mutually exclusive and collectively exhaustive events $A_1, A_2, \dots, A_k$:

$$
\sum_{i=1}^{k} P(A_i)=1
$$

---

## 2) Ways to Assign Probability

- **Classical** (equally likely outcomes):

$$
P(A)=\frac{\text{favorable outcomes}}{\text{total outcomes}}
$$

- **Relative frequency (empirical)**:

$$
P(A)\approx \frac{\text{number of times }A\text{ occurs}}{\text{total trials}}
$$

- **Subjective**: expert judgment when historical data is limited.

---

## 3) Core Probability Rules

### 3.1 Complement Rule

$$
P(A^c)=1-P(A)
$$

### 3.2 Addition Rule

General form:

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)
$$

If $A$ and $B$ are mutually exclusive:

$$
P(A\cup B)=P(A)+P(B)
$$

### 3.3 Conditional Probability

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}, \quad P(B)>0
$$

### 3.4 Multiplication Rule

$$
P(A\cap B)=P(A\mid B)P(B)=P(B\mid A)P(A)
$$

If $A$ and $B$ are independent:

$$
P(A\cap B)=P(A)P(B)
$$

---

## 4) Marginal, Joint, and Conditional Probability (Contingency Tables)

- **Joint probability**: probability two conditions occur together, e.g. $P(F\cap P)$.
- **Marginal probability**: row/column total probability, e.g. $P(F)$ or $P(P)$.
- **Conditional probability**: restricted probability, e.g. $P(F\mid P)$.

From frequency table:

$$
P(A)=\frac{\text{row/column total of }A}{N}, \qquad
P(A\cap B)=\frac{\text{cell count of }(A,B)}{N}
$$

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
$$

---

## 5) Bayes' Theorem

For events $A$ and $B$ with $P(B)>0$:

$$
P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}
$$

If $A_1,\dots,A_k$ partition the sample space:

$$
P(A_i\mid B)=\frac{P(B\mid A_i)P(A_i)}{\sum_{j=1}^{k}P(B\mid A_j)P(A_j)}
$$

Used to update prior probabilities after seeing new evidence.

---

## 6) Random Variables and Distributions

- A **distribution** describes how probability is assigned across values of a variable.
- Parameters summarize a distribution (e.g., normal uses $\mu$ and $\sigma$).

### 6.1 Discrete vs Continuous

- **Discrete**: countable values (Binomial, Poisson, Hypergeometric)
- **Continuous**: interval values (Uniform, Exponential, Normal)

---

## 7) Important Discrete Distributions

### 7.1 Binomial Distribution

Conditions: fixed $n$, independent trials, two outcomes, constant success probability $p$.

$$
X\sim \text{Bin}(n,p), \qquad P(X=x)=\binom{n}{x}p^x(1-p)^{n-x}
$$

$$
E(X)=np, \qquad Var(X)=np(1-p)
$$

### 7.2 Poisson Distribution

Counts events in fixed interval with rate $\lambda$.

$$
X\sim \text{Pois}(\lambda), \qquad P(X=x)=\frac{e^{-\lambda}\lambda^x}{x!}, \; x=0,1,2,\dots
$$

$$
E(X)=\lambda, \qquad Var(X)=\lambda
$$

### 7.3 Hypergeometric Distribution

Sampling **without replacement** from finite population.

$$
P(X=x)=\frac{\binom{K}{x}\binom{N-K}{n-x}}{\binom{N}{n}}
$$

where $N$ = population size, $K$ = number of successes in population, $n$ = sample size.

---

## 8) Important Continuous Distributions

### 8.1 Uniform Distribution

If $X\sim U(a,b)$:

$$
f(x)=\frac{1}{b-a}, \quad a\le x\le b
$$

$$
E(X)=\frac{a+b}{2}, \qquad Var(X)=\frac{(b-a)^2}{12}
$$

### 8.2 Exponential Distribution

If $X\sim \text{Exp}(\lambda)$:

$$
f(x)=\lambda e^{-\lambda x}, \quad x\ge 0
$$

$$
P(X>x)=e^{-\lambda x}, \qquad E(X)=\frac{1}{\lambda}, \qquad Var(X)=\frac{1}{\lambda^2}
$$

### 8.3 Normal Distribution

If $X\sim N(\mu,\sigma^2)$:

$$
f(x)=\frac{1}{\sigma\sqrt{2\pi}}\exp\left(-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2\right)
$$

Properties:
- bell-shaped, symmetric
- mean = median = mode
- total area under curve = 1

Standardization:

$$
Z=\frac{X-\mu}{\sigma} \sim N(0,1)
$$

---

## 9) Quick Revision Points

- Use addition rule for “or”, multiplication rule for “and”.
- Use conditional probability when information is restricted.
- Use Bayes to revise probability after evidence.
- Choose distribution by data type and experiment setup.
- For many real phenomena, normal model is a useful baseline.
