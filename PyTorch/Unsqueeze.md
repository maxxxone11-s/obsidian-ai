---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - unsqueeze
  - dimensions
  - tensor
confidence: 0.91
---

# Unsqueeze

Unsqueeze добавляет новую ось размера `1` в Tensor.

## Простое объяснение

`unsqueeze()` не меняет данные. Он добавляет новый уровень структуры, чтобы Tensor стал совместим с batch processing, channel dimension или [[Broadcasting]].

## Зачем это нужно

- Добавить batch dimension.
- Добавить channel dimension.
- Подготовить Tensor к операции с другим Tensor.

## Как это работает

Если был Tensor формы `(5,)`, то:

- `unsqueeze(0)` даст `(1, 5)`;
- `unsqueeze(1)` даст `(5, 1)`.

## Пример

```python
import torch

x = torch.randn(5)

print(x.unsqueeze(0).shape)  # torch.Size([1, 5])
print(x.unsqueeze(1).shape)  # torch.Size([5, 1])
```

## Типичные ошибки

- Неправильно выбирать позицию новой оси.
- Путать `unsqueeze(0)` и `unsqueeze(-1)`.
- Забывать, что данные не меняются, меняется только shape.

## Связанные темы

- [[Tensor]] · [[Shape]] · [[Reshape]] · [[View]] · [[Squeeze]] · [[Broadcasting]]
