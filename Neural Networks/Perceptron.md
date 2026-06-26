---
type: concept
area: Neural Networks
status: draft
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - perceptron
  - neuron
  - basic
confidence: 0
---

# Perceptron

Простейший элемент нейронной сети.

## Простое объяснение

Perceptron — это модель нейрона, которая принимает входы, применяет веса и выходит результат.

## Интуитивное объяснение

Как рецепторы в мозгу — получают сигналы, обрабатывают и выдают результат.

## Зачем это нужно

- Основа нейронных сетей
- Простейшая модель классификации
- Историческое значение

## Как это работает

### Формула
y = activation(w·x + b)

Где:
- w — веса
- x — входы
- b — смещение (bias)

## Пример

```python
import numpy as np

def perceptron(x, w, b):
    return np.sign(np.dot(w, x) + b)
```

## Типичные ошибки

- Используют perceptron для XOR задачи
- Не нормализуют входы
- Неправильно инициализируют веса

## Связанные темы

- [[Weights]] — веса в perceptron
- [[Bias]] — смещение в perceptron
- [[Activation Function]] — функция активации
- [[Neural Networks]] — многоуровневые perceptrons

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
