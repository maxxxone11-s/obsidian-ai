---
type: concept
area: PyTorch
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - pytorch
  - tensor
  - dimensions
confidence: 0.88
---

# Tensor Dimensions (ndim)

`ndim` показывает количество осей Tensor.

## Простое объяснение

Количество вложенных структур равно количеству осей. Не нужно считать числа внутри Tensor — нужно считать уровни вложенности.

## Зачем это нужно

- `ndim` помогает отличать scalar, vector, matrix и более сложные Tensor.
- Без понимания осей сложно читать [[Shape]], [[Tensor Indexing and Slicing]] и [[Broadcasting]].

## Как это работает

- Scalar -> `ndim = 0`
- Vector -> `ndim = 1`
- Matrix -> `ndim = 2`
- Далее — по количеству уровней вложенности.

## Пример

```python
import torch

print(torch.tensor(5).ndim)          # 0
print(torch.tensor([1, 2, 3]).ndim)  # 1

x = torch.tensor([
    [1, 2],
    [3, 4],
])
print(x.ndim)  # 2
```

## Типичные ошибки

- Путать `ndim` с количеством элементов.
- Считать числа вместо уровней вложенности.
- Думать, что shape `(3, 2)` означает `ndim = 3`.

## Связанные темы

- [[Tensor]] · [[Shape]] · [[Tensor Indexing and Slicing]]
