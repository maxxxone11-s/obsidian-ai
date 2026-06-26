---
type: concept
area: neural-networks
status: draft
created: 2026-06-26
updated: 2026-06-26
tags: [backpropagation, algorithm, training]
confidence: 0
---

# Backpropagation

Алгоритм обратного распространения ошибки.

## Простое объяснение

Backpropagation — это алгоритм для вычисления градиентов и обновления весов в нейронной сети.

## Интуитивное объяснение

Как отслеживание ошибки от конца сети к началу — понимаете, какие веса нужно исправить.

## Зачем это нужно

- Основа обучения нейронных сетей
- Вычисляет градиенты эффективно
- Позволяет обучать глубокие сети

## Как это работает

### Этапы
1. Forward pass — предсказание
2. Compute loss — вычисление ошибки
3. Backward pass — обратное распространение
4. Update weights — обновление весов

## Пример

```python
import torch

x = torch.tensor([1.0, 2.0], requires_grad=True)
y = (x * 2).sum()
y.backward()
print(x.grad)  # tensor([2., 2.])
```

## Типичные ошибки

- Забывают zero_grad()
- Не включают requires_grad
- Неправильная compute graph

## Связанные темы

- [[Gradient Descent]] — использует градиенты из backprop
- [[Weights]] — обновляют через backprop
- [[Loss Function]] — нужна для вычисления gradients
- [[PyTorch]] — автоматическое вычисление градиентов

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
