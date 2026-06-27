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
  - loss
  - function
  - training
confidence: 0.95
---

# Loss Function

Loss Function — функция потерь для измерения ошибки модели.

Материал разнесён по отдельным заметкам.

## Простое объяснение

Loss показывает, насколько предсказания модели отличаются от правильных ответов. Чем меньше loss, тем лучше текущий ответ модели.

## Зачем это нужно

- Без loss невозможно обучить модель.
- Именно loss минимизирует [[Gradient Descent]].
- Loss позволяет сравнивать качество разных моделей и разных шагов обучения.

## Как это работает

Loss сравнивает prediction модели с target и возвращает число ошибки.

Основные связанные функции:

- [[Machine Learning/Mathematics/MSE|MSE]] — сильнее штрафует большие ошибки за счёт квадрата.
- [[Machine Learning/Mathematics/MAE|MAE]] — усредняет абсолютную ошибку.
- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] — используется для классификации.

## Пример

```python
import torch.nn as nn

loss_fn = nn.MSELoss()
loss = loss_fn(predictions, targets)
```

## Типичные ошибки

- Думать, что loss сам исправляет модель.
- Путать [[Loss Function]] и [[Machine Learning/Mathematics/Градиент|Градиент]].
- Выбирать неподходящую функцию потерь.
- Не нормализовать выходы там, где это требуется выбранной функцией потерь.
- Забывать про weight-параметры loss-функций.

## Вопросы для проверки

- Чем отличается [[Loss Function]] от [[Machine Learning/Mathematics/Градиент|Градиент]]?
- Почему [[Machine Learning/Mathematics/MSE|MSE]] сильнее штрафует большие ошибки?

## Связанные темы

- [[Gradient Descent]] · [[Machine Learning/Mathematics/MSE|MSE]] · [[Machine Learning/Mathematics/MAE|MAE]] · [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] · [[Overfitting]]
