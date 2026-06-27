---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - reshape
  - view
  - tensor
confidence: 0.91
---

# View

View изменяет форму Tensor без копирования данных, если Tensor расположен в памяти подходящим образом.

## Простое объяснение

`view()` — это другой взгляд на те же данные. Значения не копируются, меняется только интерпретация формы.

## Зачем это нужно

- Быстро менять форму Tensor.
- Подготавливать данные для слоев модели.
- Избегать лишнего копирования памяти.

## Как это работает

Для `view()` Tensor обычно должен быть contiguous. Если Tensor стал non-contiguous после операций вроде transpose или slicing, `view()` может упасть с ошибкой. В таком случае часто используют [[Reshape]].

Общее количество элементов до и после `view()` должно совпадать.

## Пример

```python
import torch

x = torch.arange(6)
y = x.view(2, 3)
z = y.view(-1)

print(y.shape)  # torch.Size([2, 3])
print(z.shape)  # torch.Size([6])
```

## Типичные ошибки

- Использовать `view()` на non-contiguous Tensor.
- Забывать, что `-1` означает автоматический расчет размера.
- Путать `view()` с изменением самих данных.

## Связанные темы

- [[Tensor]] · [[Shape]] · [[Reshape]] · [[Unsqueeze]] · [[Squeeze]]
