---
type: concept
area: Machine Learning
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - machine-learning
  - mathematics
  - loss
  - mae
confidence: 0.95
---

# MAE

MAE — функция потерь, которая усредняет абсолютную ошибку.

## Простое объяснение

MAE показывает среднюю абсолютную разницу между prediction и target.

## Зачем это нужно

MAE используется для измерения ошибки модели, когда нужно смотреть на абсолютную величину промаха.

## Как это работает

Loss превращает ошибку модели в число. В MAE берётся абсолютная ошибка, а затем считается среднее значение.

## Пример

Prediction → абсолютная ошибка → среднее значение.

## Типичные ошибки

- Путать MAE и [[Machine Learning/Mathematics/MSE|MSE]].
- Забывать, что MSE сильнее штрафует большие ошибки за счёт квадрата.

## Связанные темы

- [[Machine Learning/Loss Function|Loss Function]] · [[Machine Learning/Mathematics/MSE|MSE]] · [[Machine Learning/Gradient Descent|Gradient Descent]]
