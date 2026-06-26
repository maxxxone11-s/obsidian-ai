---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - learning
  - backpropagation
  - algorithm
  - training
confidence: 0.95
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

## Импорт KNOWLEDGE_EXPORT — 2026-06-26

**Кратко:** Backpropagation распространяет информацию об ошибке от последнего слоя к первому и вычисляет градиенты.

**Простое объяснение:** Forward Pass отвечает. Backpropagation разбирается, кто виноват в ошибке.

**Зачем это нужно:** Именно благодаря Backpropagation нейросеть понимает, какие параметры необходимо изменить.

**Как это работает:** Backpropagation идёт от [[Loss]] назад по вычислительному графу и через [[Chain Rule]] вычисляет [[Gradient]] для каждого [[Weights|Weight]] и [[Bias]].

**Пример:** Loss → Layer 3 → Layer 2 → Layer 1.

**Типичные ошибки:**
- Думать, что Backpropagation обновляет веса.
- Представлять его как повторный Forward Pass.

**Вопросы для проверки:**
- Что делает Backpropagation?
- Почему он идет в обратном направлении?

**Следующие темы:**
- [[Gradient]]

**Связанные темы:** [[Loss]] · [[Gradient]] · [[Chain Rule]] · [[Optimizer]]
