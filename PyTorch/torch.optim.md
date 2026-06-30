---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - pytorch
  - optimizer
confidence: 0.96
difficulty: hard
---

# torch.optim

## Простое объяснение

`torch.optim` — модуль PyTorch с оптимизаторами. Optimizer получает параметры модели и обновляет их после `loss.backward()`.

## Зачем это нужно

Без optimizer модель может посчитать градиенты, но ее веса не изменятся.

## Как это работает

Базовая схема:

```text
model.parameters()
↓
optimizer
↓
loss.backward()
↓
optimizer.step()
```

`backward()` вычисляет `.grad`, а `optimizer.step()` использует эти градиенты для обновления параметров.

## Пример

```python
optimizer = torch.optim.Adam(model.parameters(), lr=0.001)
```

## Типичные ошибки

- Передавать `model` вместо `model.parameters()`.
- Думать, что optimizer работает без `backward()`.
- Путать вычисление градиентов и обновление параметров.

## Вопросы для проверки

- Что получает optimizer при создании?
- Что делает `optimizer.step()`?
- Почему optimizer не запускает forward?

## Следующие темы

- [[model.parameters()]]

## Связанные темы

- [[Neural Networks/Optimizer|Optimizer]] · [[Neural Networks/Adam|Adam]] · [[model.parameters()]] · [[Autograd]] · [[PyTorch Training Loop]]
