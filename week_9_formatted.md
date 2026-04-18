# Week 9 — Logistic Model Performance and Regression Model Building (Short Study Material)

## 1) Confusion Matrix Basics

For binary classification, outcomes are:

- **TP**: true positive
- **TN**: true negative
- **FP**: false positive
- **FN**: false negative

Misclassification error:

$$
\text{Error Rate}=\frac{FP+FN}{TP+TN+FP+FN}
$$

Accuracy:

$$
\text{Accuracy}=\frac{TP+TN}{TP+TN+FP+FN}
$$

---

## 2) Sensitivity and Specificity

Sensitivity (True Positive Rate, Recall):

$$
\text{TPR}=\frac{TP}{TP+FN}
$$

Specificity (True Negative Rate):

$$
\text{TNR}=\frac{TN}{TN+FP}
$$

False Positive Rate:

$$
\text{FPR}=\frac{FP}{FP+TN}=1-\text{Specificity}
$$

Threshold trade-off:
- lower threshold -> higher sensitivity, lower specificity
- higher threshold -> higher specificity, lower sensitivity

---

## 3) ROC Curve and AUC

ROC plots:

$$
\text{TPR} \text{ (y-axis) vs } \text{FPR} \text{ (x-axis)}
$$

for all possible thresholds.

- Curve closer to top-left is better.
- Diagonal line indicates random classifier.

AUC (Area Under Curve):

$$
0.5 \le \text{AUC} \le 1
$$

- AUC $=0.5$: no discrimination
- AUC closer to $1$: strong discrimination

---

## 4) Choosing Classification Threshold

Default threshold is often 0.5, but optimal value depends on business cost of errors.

Common criteria:

- maximize Youden index:

$$
J=\text{Sensitivity}+\text{Specificity}-1
$$

- choose threshold minimizing domain-specific cost:

$$
\text{Expected Cost}=C_{FP}\cdot FP + C_{FN}\cdot FN
$$

---

## 5) Regression Model Building (Linear Models)

Goal: build equation that best relates dependent variable $Y$ to predictors.

General linear form:

$$
Y=\beta_0+\beta_1 z_1+\beta_2 z_2+\cdots+\beta_p z_p+\varepsilon
$$

where each $z_j$ can be a transformed function of original predictors.

Key issues:
- select useful predictors
- choose proper functional form (linear, polynomial, interaction)

---

## 6) Interaction and Second-Order Terms

With two predictors $x_1, x_2$, second-order model:

$$
Y=\beta_0+\beta_1x_1+\beta_2x_2+\beta_3x_1^2+\beta_4x_2^2+\beta_5x_1x_2+\varepsilon
$$

- $x_1x_2$ captures interaction (combined effect).
- If interaction is significant, effect of one variable depends on the level of the other.

---

## 7) Model Assessment Reminders

- For logistic models: confusion matrix, ROC, AUC, threshold analysis.
- For regression models: $R^2$, adjusted $R^2$, residual checks, significance tests.
- Prefer simpler models if predictive performance is similar.

---

## 8) Quick Revision Points

- Accuracy alone is not enough; also inspect sensitivity, specificity, ROC.
- Threshold selection should follow error-cost context.
- Interaction terms are essential when predictors jointly influence response.
- Model building is iterative: form -> fit -> validate -> refine.
