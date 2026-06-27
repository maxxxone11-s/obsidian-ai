---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - scaling
  - preprocessing
  - normalization
confidence: 0.95
---

# Normalization

Normalization — это минмакс масштабирование признаков к диапазону `[0, 1]`.

## Простое объяснение

Минимальное значение становится `0`, максимальное становится `1`, а остальные значения распределяются между ними.

## Зачем это нужно

Normalization помогает привести признаки к одному диапазону, чтобы признаки с большими числами не доминировали в алгоритмах, чувствительных к расстояниям или [[Gradient Descent]].

## Как это работает

Формула:

$$X_{scaled} = \frac{X - X_{min}}{X_{max} - X_{min}}$$

Normalization сохраняет форму распределения и удобна, когда известны границы диапазона данных.

## Пример

```python
from sklearn.preprocessing import MinMaxScaler
import numpy as np

X = np.array([[1, 2], [2, 3], [3, 4], [4, 5]])

scaler = MinMaxScaler()
X_normalized = scaler.fit_transform(X)

print(X_normalized)
# [[0.   0.  ]
#  [0.33 0.33]
#  [0.67 0.67]
#  [1.   1.  ]]
```

## Типичные ошибки

- Путать Normalization и [[Standardization]].
- Использовать normalization, не понимая диапазон данных.
- Делать scaling до [[Train Test Split]].

## Связанные темы

- [[Feature Scaling]] · [[Standardization]] · [[Fit Transform и Data Leakage]] · [[KNN]] · [[SVM]]
