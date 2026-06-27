---
type: concept
area: PyTorch
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - pytorch
  - tensor
  - dtype
confidence: 0.90
---

# Tensor Dtype

Каждый Tensor имеет тип данных.

## Простое объяснение

`dtype` определяет, какие значения хранит Tensor и как PyTorch будет выполнять операции над ними.

## Зачем это нужно

- Данные модели чаще всего должны быть `float32`.
- Labels и индексы часто должны быть `int64`.
- Неверный dtype может привести к ошибкам в loss functions, embedding layers и indexing.

## Как это работает

Практическое правило:

- данные модели -> `torch.float32`;
- labels / индексы -> `torch.int64`.

PyTorch может делать type promotion: если в Tensor есть float-значение, результат часто становится float Tensor.

## Пример

```python
import torch

x = torch.tensor([1, 2, 3])
y = torch.tensor([1.0, 2.0, 3.0])

print(x.dtype)  # torch.int64
print(y.dtype)  # torch.float32
```

## Типичные ошибки

- Передавать float labels туда, где нужен `int64`.
- Использовать integer Tensor для данных модели.
- Не замечать неявное изменение dtype.

## Связанные темы

- [[Tensor]] · [[Tensor Creation]] · [[Tensor Operations]] · [[Broadcasting]]
