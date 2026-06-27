---
type: concept
area: PyTorch
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - pytorch
  - tensor
  - creation
confidence: 0.92
---

# Tensor Creation

Tensor Creation — это способы создать Tensor в PyTorch.

## Простое объяснение

PyTorch предоставляет специальные функции для быстрого создания Tensor под разные задачи: из данных, из нулей, из единиц, из случайных чисел или из диапазона.

## Зачем это нужно

- Быстро создавать входные данные для экспериментов.
- Инициализировать массивы нужной формы.
- Готовить Tensor для моделей, тестов и отладки.

## Как это работает

Основные функции:

- `torch.tensor()` — создать Tensor из Python-данных;
- `torch.zeros()` — заполнить нулями;
- `torch.ones()` — заполнить единицами;
- `torch.empty()` — выделить память без инициализации;
- `torch.rand()` — случайные числа из равномерного распределения;
- `torch.randn()` — случайные числа из нормального распределения;
- `torch.arange()` — диапазон значений.

## Пример

```python
import torch

x = torch.tensor([1, 2, 3])
y = torch.zeros((2, 3))
z = torch.rand((3, 4))
r = torch.arange(10)
```

## Типичные ошибки

- Использовать `torch.empty()` и ожидать нули.
- Путать `rand()` и `randn()`.
- Не задавать нужный `dtype`, когда он важен.

## Связанные темы

- [[Tensor]] · [[Tensor Dtype]] · [[Shape]]
