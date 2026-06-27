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
  - mse
confidence: 0.95
---

# MSE

MSE — функция потерь, которая возводит ошибку в квадрат.

## Простое объяснение

MSE показывает среднюю квадратичную ошибку. Большие ошибки штрафуются сильнее, потому что ошибка возводится в квадрат.

## Зачем это нужно

MSE используется для измерения ошибки модели, особенно в задачах регрессии.

## Как это работает

Loss превращает ошибку модели в число. В MSE разница между prediction и target возводится в квадрат, поэтому большие промахи становятся особенно заметными.

## Пример

Prediction → ошибка → квадрат ошибки → среднее значение.

## Типичные ошибки

- Думать, что MSE просто считает обычную среднюю ошибку.
- Не понимать, почему MSE сильнее штрафует большие ошибки.

## Связанные темы

- [[Machine Learning/Loss Function|Loss Function]] · [[Machine Learning/Mathematics/MAE|MAE]] · [[Machine Learning/Gradient Descent|Gradient Descent]]
