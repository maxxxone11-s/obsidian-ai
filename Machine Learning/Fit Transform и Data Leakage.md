---
type: concept
area: Machine Learning
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - machine-learning
  - preprocessing
  - data-leakage
  - scaling
confidence: 0.95
---

# Fit Transform и Data Leakage

`fit_transform` на train и `transform` на test — правило, которое помогает избежать [[Data Leakage]] при [[Feature Scaling]].

## Простое объяснение

Scaler должен "учиться" только на train-наборе. Test-набор нужно масштабировать параметрами, которые были получены из train.

## Зачем это нужно

Тестовый набор должен симулировать реальные будущие данные. Если scaler делает `fit` на test, информация из test попадает в подготовку данных, и оценка модели становится нереалистично хорошей.

## Как это работает

Правильный порядок:

1. Сначала сделать [[Train Test Split]].
2. На train выполнить `fit_transform`.
3. На test выполнить только `transform`.

## Пример

```python
from sklearn.preprocessing import StandardScaler
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

## Типичные ошибки

- Неправильно: `X_test = scaler.fit_transform(X_test)`.
- Неправильно: масштабировать все данные, а потом делать train/test split.
- Не понимать, что параметры scaling из test являются утечкой.

## Связанные темы

- [[Feature Scaling]] · [[Data Leakage]] · [[Train Test Split]] · [[Standardization]] · [[Normalization]]
