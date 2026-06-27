---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - shape
  - dimensions
  - tensor
confidence: 0.87
---

# Shape

Shape показывает количество элементов вдоль каждой оси Tensor.

## Простое объяснение

Shape отвечает не за сами данные, а за структуру [[Tensor]]. Это кортеж размеров, который говорит: сколько объектов находится на каждом уровне вложенности.

## Зачем это нужно

- Почти все ошибки PyTorch связаны именно с shape.
- Shape нужен для [[Broadcasting]], [[Reshape]], [[View]], batch processing и слоев модели.
- Shape помогает понять, подходит ли Tensor к ожидаемому входу модели.

## Как это работает

Хорошая модель: шкаф -> полки -> коробки -> предметы.

Shape показывает количество объектов на каждом уровне:

- `(3,)` — один уровень: 3 элемента;
- `(3, 2)` — 3 строки и 2 столбца;
- `(32, 3, 224, 224)` — 32 изображения, 3 RGB-канала, высота 224, ширина 224.

Важно: `shape != ndim`. Например, shape `(3, 2)` имеет две оси, а не три.

## Пример

```python
import torch

x = torch.randn(32, 3, 224, 224)

print(x.shape)  # torch.Size([32, 3, 224, 224])
print(x.ndim)   # 4
```

## Типичные ошибки

- Путать shape и ndim.
- Считать количество чисел вместо структуры.
- Неправильно определять shape после slicing.
- Забывать про batch dimension.

## Связанные темы

- [[Tensor]] · [[Tensor Dimensions (ndim)]] · [[Tensor Indexing and Slicing]] · [[Reshape]] · [[Broadcasting]]
