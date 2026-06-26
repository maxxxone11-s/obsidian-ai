---
type: concept
area: pytorch
status: draft
created: 2026-06-26
updated: 2026-06-26
tags: [pytorch, tensor, array]
confidence: 0
---

# Tensor

Основная структура данных в PyTorch.

## Простое объяснение

Tensor — это многомерный массив, похожий на NumPy array, но с поддержкой GPU и автоматического дифференцирования.

## Интуитивное объяснение

Как таблица данных, но многомерная — может быть 1D (вектор), 2D (матрица), 3D и более.

## Зачем это нужно

- Основная единица данных в PyTorch
- Эффективные вычисления на GPU
- Поддержка автоматического дифференцирования

## Как это работает

### Создание
```python
import torch
x = torch.tensor([1, 2, 3])
y = torch.zeros(3, 3)
z = torch.randn(2, 3)
```

### Свойства
- dtype (тип данных)
- device (CPU или GPU)
- shape (форма)

## Пример

```python
import torch

x = torch.tensor([[1.0, 2.0], [3.0, 4.0]])
print(x.shape)  # torch.Size([2, 2])
print(x.device)  # cpu
```

## Типичные ошибки

- Путаница между tensor и array
- Неправильное преобразование типов
- Забывают про device (CPU vs GPU)

## Связанные темы

- [[Shape]] — форма tensor
- [[View]] — изменение формы
- [[Broadcasting]] — операции между tensors
- [[Autograd]] — градиенты для tensors

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
