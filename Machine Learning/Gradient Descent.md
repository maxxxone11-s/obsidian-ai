---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - optimization
  - mathematics
  - neural-networks
  - ml
confidence: 0.95
---

# Gradient Descent

Gradient Descent — метод поиска весов, минимизирующих [[Loss Function]].

## Простое объяснение

Шаг за шагом модель двигается в сторону меньшей ошибки.

Если ошибка уменьшается — продолжаем идти. Если увеличивается — меняем направление.

## Зачем это нужно

Gradient Descent лежит в основе обучения многих моделей, включая линейные модели и нейронные сети. Именно этот алгоритм делает обучение возможным: он изменяет weight и bias, чтобы постепенно уменьшать loss.

## Как это работает

После вычисления loss и gradient алгоритм немного меняет параметры в направлении уменьшения ошибки. Затем процесс повторяется.

Формула обновления:

```text
w = w - lr * grad
```

Размер шага задаёт [[Neural Networks/Learning Rate|Learning Rate]].

## Пример

Prediction → [[Loss Function]] → [[Machine Learning/Mathematics/Градиент|Градиент]] → изменить веса → повторить.

Weight → Gradient → новый Weight.

## Типичные ошибки

- Путать Gradient Descent с [[Neural Networks/Backpropagation|Backpropagation]].
- Путать роль [[Loss Function]] и Gradient Descent.
- Не понимать, почему мы вычитаем градиент.

## Связанные темы

- [[Loss Function]] · [[Machine Learning/Mathematics/Градиент|Градиент]] · [[Neural Networks/Learning Rate|Learning Rate]] · [[Neural Networks/Optimizer|Optimizer]] · [[Feature Scaling]] · [[Scaling и Gradient Descent]]
