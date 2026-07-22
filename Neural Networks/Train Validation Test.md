---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-07-11
tags:
  - neural-networks
  - pytorch-related
  - dataset
confidence: 0.95
difficulty: easy
---

# Train Validation Test

Область: [[Neural Networks/Neural Networks|Neural Networks]]

## Простое объяснение

Train используется для изменения весов модели. Validation позволяет контролировать качество во время обучения и замечать [[Machine Learning/Overfitting]]. Test применяется один раз после завершения обучения для честной независимой оценки.

## Зачем это нужно

Правильное разделение данных позволяет оценить способность модели обобщать знания, а не запоминать обучающие примеры.

## Как это работает

- Train -> forward -> loss -> backward -> optimizer.step().
- Validation -> только forward и вычисление метрик.
- Test -> финальная проверка после окончания обучения.

## Пример

```text
dataset: 10000
train: 7000
validation: 1500
test: 1500
```

## Типичные ошибки

- Использовать Test для постоянной проверки качества во время обучения.
- Пытаться обучать модель на Validation Dataset.
- Думать о Validation как о части обучения модели, а не как об инструменте контроля инженера.

## Вопросы для проверки

- Для чего нужен Validation Dataset?
- Когда используется Test Dataset?
- Почему нельзя оценивать качество на Train Dataset?
- Что происходит только на Train?

## Следующие темы

- [[model.train() и model.eval()]]
- [[PyTorch/model.eval()|model.eval()]]

## Связанные темы

- [[Train Set]] · [[Neural Networks/Validation Set]] · [[Test Set]] · [[Machine Learning/Overfitting]] · [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]] · [[PyTorch/PyTorch Dataset|Dataset]] · [[PyTorch/DataLoader|DataLoader]]
