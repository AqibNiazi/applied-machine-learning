# Lecture 30: Function Transformer & Mathematical Transformations (Lecture 30)

This lecture covers mathematical transformations used in Machine Learning preprocessing, including Function Transformer, Power Transformer, Quantile Transformer, and methods to check normality.

---

# 🔄 What are Mathematical Transformations?

A **mathematical transformation** modifies the scale or distribution of data using a mathematical function.

## 🎯 Why Transform Data?

Many ML models (Linear Regression, Logistic Regression, SVM, etc.) assume:

- Normally distributed data
- Linear relationships
- Reduced skewness

Transformations help satisfy these assumptions and improve performance.

---

# 🔢 Types of Mathematical Transformations

| Transformation     | Formula            | Used When               |
| ------------------ | ------------------ | ----------------------- |
| Log Transform      | `log(x)`           | Right-skewed data       |
| Square Root        | `√x`               | Mild right skew         |
| Square             | `x²`               | Left-skewed data        |
| Reciprocal         | `1/x`              | Large outliers          |
| Power Transform    | `x^λ`              | General skew handling   |
| Quantile Transform | Rank-based mapping | Non-normal distribution |

---

# 🤖 Sklearn Transformer Types

| Transformer         | Purpose                            |
| ------------------- | ---------------------------------- |
| StandardScaler      | Standardization                    |
| MinMaxScaler        | Scaling between 0–1                |
| FunctionTransformer | Apply custom transformations       |
| PowerTransformer    | Make data Gaussian-like            |
| QuantileTransformer | Map to normal/uniform distribution |

---

# ⚙️ Function Transformer

`FunctionTransformer` allows applying **custom mathematical functions** to features.

## Example

```python
from sklearn.preprocessing import FunctionTransformer
import numpy as np

transformer = FunctionTransformer(np.log1p)
X_transformed = transformer.fit_transform(X)
```

## Common Function Transformations

- Log Transform
- Square Root
- Reciprocal
- Square
- Custom Lambda Function

---

# 📈 Log Transform

## Formula

```
y = log(x)
```

## Example

Original:

```
[10, 50, 100, 1000]
```

After Log Transform:

```
[2.30, 3.91, 4.60, 6.90]
```

✔ Reduces right skew

---

# 🌱 Square Root Transform

## Formula

```
y = √x
```

## Example

Original:

```
[4, 9, 16, 25]
```

After Transform:

```
[2, 3, 4, 5]
```

✔ Works for mild skew

---

# 🔁 Reciprocal Transform

## Formula

```
y = 1/x
```

## Example

Original:

```
[1, 2, 10, 100]
```

After Transform:

```
[1, 0.5, 0.1, 0.01]
```

⚠ Cannot apply to zero values

---

# 🔲 Square Transform

## Formula

```
y = x²
```

## Example

Original:

```
[1, 2, 3, 4]
```

After Transform:

```
[1, 4, 9, 16]
```

✔ Useful for left-skewed data

---

# ⚡ Power Transformer

Used to make data **more Gaussian-like**.

```python
from sklearn.preprocessing import PowerTransformer
```

## Types of Power Transformer

### 1️⃣ Box-Cox

- Works only with positive values
- Automatically finds best λ

### 2️⃣ Yeo-Johnson

- Works with positive & negative values
- More flexible

---

# 📊 Quantile Transformer

Maps data to a **uniform or normal distribution** using ranking.

```python
from sklearn.preprocessing import QuantileTransformer
```

## Output Distribution Options

- Uniform
- Normal

✔ Compresses outliers
✔ Handles highly skewed data

---

# 📉 How to Check if Data is Normal?

Methods:

- Histogram
- Skewness value
- QQ Plot
- Shapiro-Wilk Test
- Kolmogorov-Smirnov Test

---

# 📌 QQ Plot (Quantile-Quantile Plot)

A graphical method to compare dataset distribution with a normal distribution.

- Points on straight line → Normal distribution
- S-shape → Right skew
- Reverse S → Left skew

---

# 🧠 When to Use Which Transform?

| Data Condition          | Recommended Transform |
| ----------------------- | --------------------- |
| Right skew              | Log / √ / Power       |
| Extreme outliers        | Reciprocal            |
| Left skew               | Square                |
| Mixed distribution      | Quantile              |
| Positive-only skew      | Box-Cox               |
| Negative values present | Yeo-Johnson           |

---

# ✅ Summary

- Transformations improve data distribution
- Help satisfy ML model assumptions
- Power & Quantile transformers automate normalization
- Always check distribution before & after transformation
- Use QQ plots for visual normality verification
