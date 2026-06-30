---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - machine-learning
  - mathematics
  - loss
  - cross-entropy
confidence: 0.95
difficulty: hard
---

# Cross Entropy

Cross Entropy — функция потерь для классификации.

## Простое объяснение

Cross Entropy измеряет ошибку классификационной модели.
В PyTorch ее практическая реализация для multi-class задач — [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]].

## Зачем это нужно

Она используется там, где модель должна выбрать класс, а loss нужен для обучения через [[Gradient Descent]].

## Как это работает

Cross Entropy связана с вероятностями классов, [[Neural Networks/Logits|Logits]], [[Neural Networks/Softmax|Softmax]] и [[Entropy]].

В `CrossEntropyLoss` PyTorch ожидает logits и правильные индексы классов, а Softmax/LogSoftmax применяется внутри loss-функции.

## Пример

```text
logits -> LogSoftmax -> NLLLoss -> Cross Entropy loss
```

## Типичные ошибки

- Путать Cross Entropy с [[Machine Learning/Mathematics/MSE|MSE]].
- Использовать неподходящую функцию потерь для классификации.
- Добавлять Softmax перед [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]].

## Вопросы для проверки

- Почему Cross Entropy подходит для классификации?
- Почему `CrossEntropyLoss` принимает logits, а не вероятности?
- Что происходит с правильным классом внутри loss?

## Следующие темы

- [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]]

## Связанные темы

- [[Machine Learning/Loss Function|Loss Function]] · [[Entropy]] · [[Neural Networks/Softmax|Softmax]] · [[Neural Networks/Logits|Logits]] · [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]]
