---
type: concept
area: PyTorch
status: needs_review
created: 2026-06-27
updated: 2026-06-27
tags:
  - pytorch
  - tensor
  - indexing
  - slicing
confidence: 0.72
---

# Tensor Indexing and Slicing

Tensor индексируется почти так же, как ndarray в NumPy.

## Простое объяснение

В двумерном Tensor запись читается как `Tensor[rows, columns]`.

Запятая разделяет оси, а не означает условие.

## Зачем это нужно

- Доставать строки, столбцы и части Tensor.
- Готовить batch и feature slices.
- Понимать, почему после indexing или slicing меняется [[Shape]].

## Как это работает

Основные формы:

- `x[row]` — взять строку или элемент по первой оси;
- `x[row, column]` — взять значение по строке и столбцу;
- `x[:, column]` — все строки и один столбец;
- `x[row, :]` — одна строка и все столбцы.

Indexing часто уменьшает размерность, slicing чаще сохраняет её.

## Пример

```python
import torch

x = torch.tensor([
    [10, 20, 30],
    [40, 50, 60],
])

print(x[:, 1])   # все строки, второй столбец -> tensor([20, 50])
print(x[1, :])   # вторая строка -> tensor([40, 50, 60])
print(x[0].shape)   # torch.Size([3])
print(x[:1].shape)  # torch.Size([1, 3])
```

## Типичные ошибки

- Воспринимать запятую как условие.
- Путать строки и столбцы.
- Ошибаться при определении shape после slicing.
- Не различать `x[0]` и `x[:1]`.

## Связанные темы

[[Tensor]] · [[Shape]] · [[Tensor Dimensions (ndim)]] · [[Reshape]]
