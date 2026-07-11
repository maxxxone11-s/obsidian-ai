---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-07-11
tags: [machine-learning, scaling, preprocessing, standardization]
aliases: [Feature Standardization, Standardization in Machine Learning, Стандартизация признаков]
confidence: 0.95
difficulty: beginner
---

# Feature Standardization

## Академическое определение

Feature Standardization — preprocessing-преобразование признаков по z-score, при котором из каждого значения вычитается среднее train-признака, а результат делится на его стандартное отклонение.

## Инженерное назначение

Feature Standardization приводит признаки к сопоставимому масштабу, помогая distance-based алгоритмам и gradient-based optimization работать стабильнее.

## Причина существования

Признаки с большими числовыми диапазонами могут непропорционально влиять на расстояния и шаги оптимизации. Кроме того, параметры scaling должны вычисляться только на train data, иначе возникает Data Leakage.

## Простое объяснение

Каждый признак преобразуется так, чтобы на train data его среднее было около `0`, а стандартное отклонение — около `1`.

## Как это работает

1. После train/test split scaler обучается через `fit` только на train data.
2. Для каждого признака сохраняются `μ` и `σ` train-набора.
3. Train, validation и test преобразуются через `(x - μ) / σ` с одинаковыми параметрами.
4. Модель обучается на признаках сопоставимого масштаба.

## Пример

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

## Типичные ошибки

- Путать Feature Standardization и [[Machine Learning/Normalization|Normalization]].
- Выполнять `fit_transform` отдельно на test data.
- Вычислять параметры scaling до train/test split.
- Считать, что все tree-based модели обязательно требуют standardization.

## Связанные темы

[[Machine Learning/Feature Scaling|Feature Scaling]] · [[Machine Learning/Normalization|Normalization]] · [[Machine Learning/Fit Transform и Data Leakage|Fit Transform и Data Leakage]] · [[Machine Learning/Scaling и Gradient Descent|Scaling и Gradient Descent]] · [[Machine Learning/SVM|SVM]] · [[Statistics/Z-score Standardization|Z-score Standardization]]

## Вопросы для проверки

- Почему scaler обучается только на train data?
- Какие параметры сохраняет StandardScaler?
- Для каких алгоритмов масштаб признаков особенно важен?

## Следующие темы

[[Machine Learning/Fit Transform и Data Leakage|Fit Transform и Data Leakage]] · [[Machine Learning/Scaling для KNN и SVM|Scaling для KNN и SVM]]
