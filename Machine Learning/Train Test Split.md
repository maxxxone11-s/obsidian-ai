---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - evaluation
  - train
  - test
  - split
  - data
confidence: 0.95
---

# Train/Test Split

Разделение данных на обучающий и тестовый наборы.

## Интуитивное объяснение

Как учеба и экзамен — готовитесь на одних материалах, проверяетесь на других.

## Кратко

Train используется для обучения. Test — только для проверки качества модели.

## Простое объяснение

Train/Test Split делит данные на две части: одну для обучения модели, другую для проверки.

Train — подготовка. Test — экзамен.

## Зачем это нужно

- Проверка обобщающей способности модели
- Избежание переобучения
- Объективная оценка качества

Позволяет понять способность модели обобщать знания.

## Как это работает

### Классический подход
- Обычно 80% train, 20% test
- Иногда добавляют validation set

Данные делят на обучающую и тестовую части. Модель учится только на train, а test используется как имитация новых данных.

## Пример

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

80% Train / 20% Test.

## Типичные ошибки

- Утечка данных из test в train
- Неправильный порядок (масштабировать после split)
- Забывают про random_state для воспроизводимости

- Использовать Test при обучении.

## Вопросы для проверки

- Почему нельзя обучаться на Test?

## Следующие темы

- [[Data Leakage]]

## Связанные темы

- [[Feature Scaling]] — масштабировать после split!
- [[Overfitting]] — проверяют с test set
- [[Loss Function]] — вычисляют на обоих наборах

- [[Cross Validation]] · [[Overfitting]]
