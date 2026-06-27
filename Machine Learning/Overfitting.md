---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - evaluation
  - overfitting
  - generalization
  - bias
confidence: 0.95
---

# Overfitting

Overfitting — ситуация, когда модель слишком хорошо учится на обучающих данных и плохо обобщает.

## Простое объяснение

Overfitting — это когда модель запомнила train-данные и шум, а не поняла общую закономерность.

## Зачем это нужно

- Избежать переобучения.
- Улучшить обобщение модели.
- Выбрать правильный размер модели.
- Проверять качество не только на train, но и на test.

## Как это работает

Признаки overfitting:

- низкая потеря на train;
- высокая потеря на test;
- модель слишком сложная;
- мало данных для обучения.

Как уменьшить overfitting:

- регуляризация;
- dropout;
- early stopping;
- больше данных;
- менее сложная модель.

## Пример

```python
# Признак overfitting: train_loss << test_loss
print(f"Train loss: {train_loss}")  # низкая
print(f"Test loss: {test_loss}")    # высокая
```

## Типичные ошибки

- Использовать только train-метрики.
- Не проверять модель на test set.
- Брать слишком большую модель.
- Слишком долго обучать модель.

## Связанные темы

- [[Underfitting]] · [[Train Test Split]] · [[Loss Function]] · [[Cross Validation]] · [[Neural Networks/Dropout|Dropout]]
