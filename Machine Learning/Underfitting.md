---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - evaluation
  - underfitting
  - bias
  - model-capacity
confidence: 0.95
---

# Underfitting

Underfitting — ситуация, когда модель слишком простая и не может выучить закономерности в данных.

## Простое объяснение

Underfitting — это когда модель ничего не поняла: плохо работает и на train, и на test.

## Зачем это нужно

- Правильно выбрать сложность модели.
- Убедиться, что модель достаточно мощная.
- Диагностировать проблемы обучения.

## Как это работает

Признаки underfitting:

- высокая потеря на train;
- высокая потеря на test;
- модель слишком простая;
- низкая производительность везде.

Как уменьшить underfitting:

- увеличить сложность модели;
- добавить параметры;
- улучшить признаки через [[Feature Engineering]];
- ослабить слишком сильную регуляризацию.

## Пример

```python
# Признак underfitting: train_loss высокая везде
print(f"Train loss: {train_loss}")  # высокая
print(f"Test loss: {test_loss}")    # высокая
```

## Типичные ошибки

- Использовать слишком простую модель.
- Давать модели недостаточно признаков.
- Делать слишком сильную регуляризацию.
- Путать underfitting с [[Overfitting]].

## Связанные темы

- [[Overfitting]] · [[Train Test Split]] · [[Loss Function]] · [[Feature Engineering]] · [[Cross Validation]]
