---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - loss
  - logging
confidence: 0.99
difficulty: easy
---

# loss.item()

## Простое объяснение

`loss.item()` преобразует Tensor с одним числом в обычное число Python.

## Зачем это нужно

Так можно логировать loss и накапливать значения вне вычислительного графа.

## Как это работает

```text
tensor(0.52)
↓
0.52
```

## Пример

```python
train_loss += loss.item()
```

## Типичные ошибки

- Пытаться складывать Tensor вместо чисел.
- Забывать, что `item()` подходит только для Tensor с одним элементом.

## Вопросы для проверки

- Что возвращает `item()`?
- Почему это удобно для logging?

## Следующие темы

- Logging

## Связанные темы

- [[Weighted Average Loss]] · [[PyTorch Training Loop]]
