---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - machine-learning
  - mathematics
  - probability
  - neural-networks
confidence: 0.95
difficulty: medium
---

# Logits

## Кратко

Logits — сырые выходные значения нейросети.

## Простое объяснение

Logits — это сырые числа, которые показывают уверенность модели до преобразования в вероятности. Это еще не вероятности.

## Зачем это нужно

Большинство PyTorch loss-функций для классификации ожидают именно logits. Например, [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]] сам применяет LogSoftmax внутри.

## Как это работает

Последний Linear возвращает сырые оценки:

```text
[2.3, 5.1, -0.7]
```

Это еще не вероятности. После Softmax их можно интерпретировать как распределение по классам:

```text
[0.05, 0.92, 0.03]
```

## Пример

```python
outputs = model(x)
# outputs — logits
```

## Типичные ошибки

- Считать logits вероятностями.
- Использовать argmax до понимания роли Softmax.
- Передавать probabilities в loss, который ожидает logits.

## Вопросы для проверки

- Что такое logits?
- Чем logits отличаются от вероятностей?
- Почему модель возвращает logits?

## Следующие темы

- [[Neural Networks/Softmax|Softmax]]
- [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]]

## Связанные темы

- [[Feature]] · [[Activation Function]] · [[Model]] · [[Neural Networks/Softmax|Softmax]] · [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]]
