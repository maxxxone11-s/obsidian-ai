---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-28
tags:
  - pytorch
  - autograd
  - gradient
confidence: 0.90
---

# Autograd

Автоматическое дифференцирование в PyTorch.

## Кратко

Изучена идея автоматического вычисления производных.

## Простое объяснение

Autograd строит граф вычислений и автоматически считает производные.

## Интуитивное объяснение

Как система вычисления влияния каждого параметра на результат.

## Зачем это нужно

- Вычисление градиентов для обучения
- Автоматическое дифференцирование
- Упрощение кода обучения

Без Autograd обучение современных нейросетей невозможно.

## Как это работает

### Механизм
- requires_grad флаг
- Построение вычислительного графа
- backward() для вычисления градиентов
- После `backward()` появляются `.grad`

Autograd — автоматический вычислитель производных по computation graph.

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
- Думать, что `requires_grad` хранит историю состояний Tensor.
- Путать `x.backward()` и `loss.backward()`.

## Вопросы для проверки

- Что делает `requires_grad=True`?
- Когда появляется `.grad`?
- Что делает `backward()`?
- Почему сначала `.grad == None`?

## Следующие темы

- [[Machine Learning/Gradient Descent|Gradient Descent]]

## Связанные темы

- [[Tensor]] — требует requires_grad
- [[Backpropagation]] — использует autograd
- [[Weights]] — градиенты для весов
- [[Gradient Descent]] — использует градиенты
- [[Algorithms/Graph Theory/DAG/PyTorch Computation Graph|Computation Graph]]
- [[Neural Networks/Derivative|Derivative]]

## Связь с Tensor Fundamentals

[[Broadcasting]] и [[Tensor Operations]] ведут к [[Autograd]]: как только операции участвуют в вычислении loss, PyTorch может построить вычислительный граф и посчитать градиенты.
