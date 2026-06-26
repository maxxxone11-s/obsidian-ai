---
type: concept
area: neural-networks
status: draft
created: 2026-06-26
updated: 2026-06-26
tags: [activation, nonlinearity, function]
confidence: 0
---

# Activation Function

Функция активации для введения нелинейности.

## Простое объяснение

Activation Function преобразует сумму взвешенных входов, добавляя нелинейность.

## Интуитивное объяснение

Как включатель света — пока не достигнешь порога, ничего не происходит, потом резко включается.

## Зачем это нужно

- Добавляет нелинейность
- Позволяет сети учиться сложным функциям
- Без неё сеть просто линейная модель

## Как это работает

### Основные функции
- ReLU (Rectified Linear Unit)
- Sigmoid
- Tanh
- Softmax

### Свойства
- Должны быть дифференцируемыми
- Часто ограничены в диапазоне

## Пример

```python
import torch.nn as nn

relu = nn.ReLU()
x = torch.tensor([-1.0, 0.0, 1.0])
print(relu(x))  # tensor([0., 0., 1.])
```

## Типичные ошибки

- Используют sigmoid везде (dying sigmoid)
- Забывают про activation function
- Неправильно выбирают для задачи

## Связанные темы

- [[Perceptron]] — применяется после взвешенной суммы
- [[Weights]] — перед activation
- [[Bias]] — перед activation
- [[Backpropagation]] — нужна производная

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
