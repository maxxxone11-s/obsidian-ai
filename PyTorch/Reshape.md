---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - reshape
  - tensor
confidence: 0.91
---

# Reshape

Reshape изменяет форму Tensor без изменения самих данных.

## Простое объяснение

`reshape()` пересобирает структуру Tensor: значения остаются теми же, но меняется то, как они организованы по осям.

## Зачем это нужно

- Подготовить данные к слою модели.
- Превратить плоский Tensor в матрицу или обратно.
- Работать с batch, channel и feature dimensions.

## Как это работает

Количество элементов до и после reshape должно оставаться одинаковым.

`-1` означает: PyTorch сам вычислит этот размер по общему количеству элементов.

`reshape()` обычно безопаснее, чем [[View]], потому что может работать с non-contiguous Tensor и при необходимости создать копию.

## Пример

```python
import torch

x = torch.arange(12)
y = x.reshape(3, 4)
z = y.reshape(-1)

print(y.shape)  # torch.Size([3, 4])
print(z.shape)  # torch.Size([12])
```

## Типичные ошибки

- Менять shape так, что общее количество элементов не совпадает.
- Забывать про `-1` для автоматического расчета.
- Путать `reshape()` и `view()`.

## Связанные темы

[[Tensor]] · [[Shape]] · [[View]] · [[Unsqueeze]] · [[Squeeze]] · [[Tensor Indexing and Slicing]] · [[Broadcasting]]
