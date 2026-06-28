---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-28
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

## Кратко

Понято, откуда появляется Loss в реальной модели.

## Простое объяснение

Loss показывает, насколько предсказания модели отличаются от правильных ответов. Чем меньше loss, тем лучше текущий ответ модели.

Loss сравнивает предсказание модели с правильным ответом.

## Зачем это нужно

- Без loss невозможно обучить модель.
- Именно loss минимизирует [[Gradient Descent]].
- Loss позволяет сравнивать качество разных моделей и разных шагов обучения.

Loss определяет, насколько хорошо работает модель.

## Как это работает

Loss сравнивает prediction модели с target и возвращает число ошибки.

Loss зависит не только от весов, а от результата работы модели. Во время обучения меняются только веса и bias.

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

```text
prediction = 6
label = 12
Loss = (6 - 12)^2
```

## Типичные ошибки

- Думать, что loss сам исправляет модель.
- Путать [[Loss Function]] и [[Machine Learning/Mathematics/Градиент|Градиент]].
- Выбирать неподходящую функцию потерь.
- Не нормализовать выходы там, где это требуется выбранной функцией потерь.
- Забывать про weight-параметры loss-функций.
- Думать, что Loss зависит только от weight.
- Интерпретировать искусственный пример `Loss = w²` как реальную модель.

## Вопросы для проверки

- Чем отличается [[Loss Function]] от [[Machine Learning/Mathematics/Градиент|Градиент]]?
- Почему [[Machine Learning/Mathematics/MSE|MSE]] сильнее штрафует большие ошибки?
- От чего зависит Loss?
- Что меняется во время обучения?
- Почему данные не изменяются?
- Почему меняются только веса?

## Следующие темы

- [[PyTorch/PyTorch Training Loop|Training Loop]]

## Связанные темы

- [[Gradient Descent]] · [[Machine Learning/Mathematics/MSE|MSE]] · [[Machine Learning/Mathematics/MAE|MAE]] · [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] · [[Overfitting]]
