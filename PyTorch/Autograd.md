---
type: concept
area: PyTorch
status: draft
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - autograd
  - gradient
confidence: 0
---

# Autograd

Автоматическое дифференцирование в PyTorch.

## Простое объяснение

Autograd автоматически вычисляет градиенты для обратного распространения.

## Интуитивное объяснение

Как система вычисления влияния каждого параметра на результат.

## Зачем это нужно

- Вычисление градиентов для обучения
- Автоматическое дифференцирование
- Упрощение кода обучения

## Как это работает

### Механизм
- requires_grad флаг
- Построение вычислительного графа
- backward() для вычисления градиентов

## Пример

```python
import torch

x = torch.tensor([2.0], requires_grad=True)
y = x ** 2
y.backward()
print(x.grad)  # tensor([4.])
```

## Типичные ошибки

- Забывают requires_grad=True
- Не вызывают backward()
- Забывают zero_grad() между итерациями

## Связанные темы

- [[Tensor]] — требует requires_grad
- [[Backpropagation]] — использует autograd
- [[Weights]] — градиенты для весов
- [[Gradient Descent]] — использует градиенты

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки

## Связь с Tensor Fundamentals

[[Broadcasting]] и [[Tensor Operations]] ведут к [[Autograd]]: как только операции участвуют в вычислении loss, PyTorch может построить вычислительный граф и посчитать градиенты.
