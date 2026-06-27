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
  - standardization
confidence: 0.95
---

# Standardization

Standardization — это z-score масштабирование признаков.

## Простое объяснение

Standardization преобразует признаки так, чтобы среднее было `0`, а стандартное отклонение было `1`.

## Зачем это нужно

Standardization часто используется как default-вариант scaling. Она помогает алгоритмам на основе расстояний и методам оптимизации работать стабильнее.

## Как это работает

Формула:

$$X_{scaled} = \frac{X - \mu}{\sigma}$$

Где:

- `μ` — среднее значение;
- `σ` — стандартное отклонение.

## Пример

```python
from sklearn.preprocessing import StandardScaler
import numpy as np

X = np.array([[1, 2], [2, 3], [3, 4], [4, 5]])

scaler = StandardScaler()
X_standardized = scaler.fit_transform(X)

print(X_standardized)
# [[-1.46 -1.46]
#  [-0.49 -0.49]
#  [ 0.49  0.49]
#  [ 1.46  1.46]]
```

## Типичные ошибки

- Путать Standardization и [[Normalization]].
- Делать `fit_transform` на test-наборе.
- Забывать, что параметры scaling должны быть рассчитаны только на train.

## Связанные темы

- [[Feature Scaling]] · [[Normalization]] · [[Fit Transform и Data Leakage]] · [[Scaling и Gradient Descent]] · [[SVM]]
