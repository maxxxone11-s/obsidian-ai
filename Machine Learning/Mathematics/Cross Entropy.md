---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - mathematics
  - loss
  - cross-entropy
confidence: 0.95
---

# Cross Entropy

Cross Entropy — функция потерь для классификации.

## Простое объяснение

Cross Entropy измеряет ошибку классификационной модели.

## Зачем это нужно

Она используется там, где модель должна выбрать класс, а loss нужен для обучения через [[Gradient Descent]].

## Как это работает

В исходном материале Cross Entropy отмечена как loss для классификации. Она связана с вероятностями классов, [[Neural Networks/Logits|Logits]], [[Neural Networks/Softmax|Softmax]] и [[Entropy]].

## Пример

Prediction class probabilities → target class → Cross Entropy loss.

## Типичные ошибки

- Путать Cross Entropy с [[Machine Learning/Mathematics/MSE|MSE]].
- Использовать неподходящую функцию потерь для классификации.

## Связанные темы

- [[Machine Learning/Loss Function|Loss Function]] · [[Entropy]] · [[Neural Networks/Softmax|Softmax]] · [[Neural Networks/Logits|Logits]]
