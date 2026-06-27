---
type: concept
area: Machine Learning
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - machine-learning
  - scaling
  - knn
  - svm
confidence: 0.95
---

# Scaling для KNN и SVM

[[KNN]] и [[SVM]] чувствительны к масштабу признаков, потому что используют расстояния в feature space.

## Простое объяснение

Если один признак измеряется в тысячах, а другой в единицах, признак с большими числами может полностью доминировать в расстоянии.

## Зачем это нужно

Scaling критичен для:

- [[KNN]] — основан на расстояниях между точками;
- [[SVM]] — использует расстояния в feature space.

## Как это работает

[[Feature Scaling]] делает признаки сопоставимыми. После этого расстояния отражают структуру данных, а не просто разные единицы измерения.

## Пример

При сравнении квартир цена в миллионах может доминировать над площадью в квадратных метрах просто из-за масштаба чисел. Scaling переводит признаки в сопоставимый масштаб.

```python
from sklearn.preprocessing import StandardScaler
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC

iris = load_iris()
X, y = iris.data, iris.target

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

model = SVC()
model.fit(X_train_scaled, y_train)
accuracy = model.score(X_test_scaled, y_test)
print(f"Accuracy: {accuracy:.2f}")
```

## Типичные ошибки

- Запускать KNN без scaling.
- Запускать SVM без scaling.
- Думать, что большие числа автоматически означают более важный признак.

## Связанные темы

- [[Feature Scaling]] · [[Normalization]] · [[Standardization]] · [[KNN]] · [[SVM]]
