# Week 1 — Data Analytics with Python (Short Study Material)

## 1) Introduction to Data Analytics

Data analytics is the process of collecting, cleaning, transforming, analyzing, and interpreting data for better decisions.

- The key skill is **choosing the right method** and **interpreting results correctly**.
- Software can compute quickly, but conceptual understanding prevents wrong conclusions.
- Typical analytics types:
  - **Descriptive**: What happened?
  - **Diagnostic**: Why did it happen?
  - **Predictive**: What is likely to happen?
  - **Prescriptive**: What should be done?

---

## 2) Python Fundamentals (Week 1 scope)

### Setup (Anaconda)
1. Open `www.anaconda.com`
2. Download Anaconda (Python 3.x)
3. Install and follow setup instructions

### Basic pandas access patterns

Assume `df` is a DataFrame.

- `df.head()` → first 5 rows
- `df.tail(1)` → last row
- `df.loc[0]` → first row by label/index
- `df.loc[[0, 99, 999]]` → multiple selected rows
- `df.iloc[0]` → first row by position
- `df.iloc[:, 0]` → first column
- `df.iloc[0:5, 1:3]` → row and column slice

---

## 3) Central Tendency

Central tendency gives a single representative value for a dataset.

### 3.1 Arithmetic Mean

Population mean:

$$
\mu = \frac{\sum_{i=1}^{N} X_i}{N}
$$

Sample mean:

$$
\bar{x} = \frac{\sum_{i=1}^{n} x_i}{n}
$$

- Uses all observations
- Sensitive to outliers

### 3.2 Weighted Mean

$$
\bar{x}_w = \frac{\sum_{i=1}^{n} w_i x_i}{\sum_{i=1}^{n} w_i}
$$

Use when values have different importance (weights).

### 3.3 Median

- Sort data first.
- If $n$ is odd: median is value at position $\frac{n+1}{2}$.
- If $n$ is even: median is average of values at positions $\frac{n}{2}$ and $\frac{n}{2}+1$.

### 3.4 Percentile

$P_k$ is the value below which $k\%$ of observations lie.

Common rank position:

$$
L = \frac{k}{100}(n+1)
$$

(Interpolate if $L$ is not an integer.)

---

## 4) Dispersion (Spread)

### 4.1 Range

$$
\text{Range} = X_{\max} - X_{\min}
$$

### 4.2 Interquartile Range (IQR)

$$
\text{IQR} = Q_3 - Q_1
$$

### 4.3 Variance

Population variance:

$$
\sigma^2 = \frac{\sum_{i=1}^{N}(X_i-\mu)^2}{N}
$$

Sample variance:

$$
s^2 = \frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}
$$

### 4.4 Standard Deviation

$$
\sigma = \sqrt{\sigma^2}, \qquad s = \sqrt{s^2}
$$

### 4.5 Standard Score (Z-score)

Population form:

$$
z = \frac{x-\mu}{\sigma}
$$

Sample form:

$$
z = \frac{x-\bar{x}}{s}
$$

### 4.6 Coefficient of Variation (CV)

$$
CV = \frac{\sigma}{\mu}\times 100\% \qquad \text{or} \qquad CV = \frac{s}{\bar{x}}\times 100\%
$$

---

## 5) Distribution Shape

### 5.1 Skewness

- **Positive skew**: longer right tail
- **Negative skew**: longer left tail
- **Zero skew**: symmetric

Quick Pearson approximation:

$$
\text{Skewness} \approx \frac{3(\bar{x}-\text{Median})}{s}
$$

### 5.2 Kurtosis

- **Leptokurtic**: sharper peak, heavier tails
- **Mesokurtic**: normal-like
- **Platykurtic**: flatter peak, lighter tails

---

## 6) Empirical Rule (Normal Distribution)

For bell-shaped normal data:

$$
P(\mu-\sigma \le X \le \mu+\sigma) \approx 0.68
$$

$$
P(\mu-2\sigma \le X \le \mu+2\sigma) \approx 0.95
$$

$$
P(\mu-3\sigma \le X \le \mu+3\sigma) \approx 0.997
$$

Equivalent notation: **68%–95%–99.7% rule**.

> Note: This rule is valid only when the distribution is approximately normal (bell-shaped).

---

## 7) Box-and-Whisker Plot Essentials

- Box spans from $Q_1$ to $Q_3$.
- Center line in box is the median.
- IQR controls spread of middle 50%.
- Common outlier fences:

$$
\text{Lower Fence} = Q_1 - 1.5\,\text{IQR}
$$

$$
\text{Upper Fence} = Q_3 + 1.5\,\text{IQR}
$$

---

## 8) Data Visualization (Theory)

- **Histogram**: distribution shape
- **Box plot**: spread, median, outliers
- **Bar chart**: category comparisons
- **Line chart**: trend over time
- **Scatter plot**: relationship between two numeric variables

---

## 9) Quick Revision Points

- Prefer median + IQR when outliers are strong.
- Prefer mean + SD for roughly symmetric/normal data.
- Always pair a center measure with a spread measure.
- Use z-score for cross-scale comparison.
- Use empirical rule only for near-normal distributions.
