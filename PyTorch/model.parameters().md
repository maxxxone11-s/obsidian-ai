---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - parameters
  - optimizer
confidence: 0.99
difficulty: easy
---

# model.parameters()

## Простое объяснение

`model.parameters()` возвращает все обучаемые параметры модели: веса и bias, которые могут изменяться во время обучения.

## Зачем это нужно

Optimizer должен знать, какие параметры обновлять после `backward()`.

## Как это работает

```text
model.parameters()
↓
l1.weight
l1.bias
l2.weight
l2.bias
```

Эти параметры передаются в optimizer, например в [[torch.optim]] или Adam.

## Пример

```python
optimizer = torch.optim.Adam(model.parameters(), lr=0.001)
```

## Типичные ошибки

- Передавать `model` вместо `model.parameters()`.
- Думать, что optimizer получает весь объект модели, а не список trainable parameters.

## Вопросы для проверки

- Что возвращает `model.parameters()`?
- Почему optimizer работает именно с `parameters()`?

## Следующие темы

- State Dict

## Связанные темы

- [[nn.Module]] · [[nn.Linear]] · [[torch.optim]] · [[Neural Networks/Adam|Adam]] · [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]]
