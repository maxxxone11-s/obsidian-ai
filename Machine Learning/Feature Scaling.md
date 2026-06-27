---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - data-preparation
  - preprocessing
  - scaling
confidence: 0.95
last_review: 2026-06-26
next_review: 2026-07-10
---

# Feature Scaling

Feature Scaling — это приведение признаков к сопоставимому масштабу.

Материал разнесён по отдельным заметкам.

## Простое объяснение

Feature Scaling нужен, чтобы все признаки "говорили на одном языке" и не доминировал тот, у которого просто большие числа.

## Зачем это нужно

- Ускоряет обучение моделей.
- Помогает алгоритмам, чувствительным к масштабу: [[KNN]], [[SVM]], [[Neural Networks]].
- Делает признаки сопоставимыми.
- Улучшает сходимость методов на основе [[Gradient Descent]].

## Как это работает

Основные способы и связанные темы:

- [[Normalization]] — приведение значений к диапазону `[0, 1]`.
- [[Standardization]] — преобразование признаков так, чтобы среднее было `0`, а стандартное отклонение `1`.
- [[Fit Transform и Data Leakage]] — как масштабировать train/test без утечки данных.
- [[Scaling и Gradient Descent]] — почему масштабирование помогает оптимизации.
- [[Scaling для KNN и SVM]] — почему расстояния чувствительны к масштабу.
- [[Scaling и Tree-Based Models]] — почему деревьям scaling почти не нужен.

## Пример

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

## Типичные ошибки

- Масштабировать test через `fit_transform`.
- Масштабировать данные до [[Train Test Split]].
- Не понимать, почему [[Decision Tree]], [[Random Forest]] и [[XGBoost]] почти не требуют scaling.
- Не различать [[Normalization]] и [[Standardization]].

## Что повторить позже

- [ ] Понять разницу между [[Normalization]] и [[Standardization]].
- [ ] Отработать `fit_transform` на train и `transform` на test.
- [ ] Понять, почему масштабирование помогает [[Gradient Descent]].
- [ ] Запомнить, для каких алгоритмов scaling критичен.
- [ ] Применить scaling в собственном ML-проекте.
- [ ] Проверить разницу в точности модели с масштабированием и без.

## Связанные темы

- [[Normalization]] · [[Standardization]] · [[Fit Transform и Data Leakage]] · [[Scaling и Gradient Descent]] · [[Scaling для KNN и SVM]] · [[Scaling и Tree-Based Models]]
