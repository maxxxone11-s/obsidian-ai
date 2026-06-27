---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - squeeze
  - dimensions
  - tensor
confidence: 0.91
---

# Squeeze

Squeeze удаляет оси размера `1` из Tensor.

## Простое объяснение

`squeeze()` убирает лишние уровни структуры, но не меняет значения. Это обратная операция к [[Unsqueeze]].

## Зачем это нужно

- Убрать лишний batch dimension, если batch size равен 1.
- Упростить форму Tensor перед дальнейшими вычислениями.
- Подготовить вывод модели к метрикам или визуализации.

## Как это работает

Без аргумента `squeeze()` удаляет все размерности размера `1`. С аргументом удаляет только конкретную ось, если её размер равен `1`.

## Пример

```python
import torch

x = torch.randn(1, 3, 1, 4)

print(x.squeeze().shape)   # torch.Size([3, 4])
print(x.squeeze(0).shape)  # torch.Size([3, 1, 4])
```

## Типичные ошибки

- Случайно удалить больше осей, чем ожидалось.
- Применить `squeeze(dim)` к оси, размер которой не равен `1`.
- Путать [[Squeeze]] и [[Unsqueeze]].

## Связанные темы

- [[Tensor]] · [[Shape]] · [[Reshape]] · [[View]] · [[Unsqueeze]]
