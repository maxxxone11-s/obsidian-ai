---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - ml-engineering
  - configuration
confidence: 0.98
difficulty: easy
---

# config.py

## Простое объяснение

`config.py` хранит изменяемые настройки проекта отдельно от логики обучения.

## Зачем это нужно

Так можно быстро менять настройки без изменения кода training loop или архитектуры модели.

## Как это работает

Обычно хранит:

- `batch_size`;
- `learning_rate`;
- `epochs`;
- `hidden_size`;
- `input_size`;
- `num_classes`.

Не все эти значения являются гиперпараметрами: часть выбирает инженер, а часть определяется датасетом.

## Пример

```python
LEARNING_RATE = 0.001
BATCH_SIZE = 64
EPOCHS = 10
```

## Типичные ошибки

- Захардкодить значения в `train.py`.
- Хранить настройки в нескольких файлах.
- Считать `input_size` и `num_classes` гиперпараметрами.

## Вопросы для проверки

- Почему настройки выносят отдельно?
- Какие параметры определяются инженером?
- Какие параметры определяются датасетом?

## Следующие темы

- [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]]

## Связанные темы

- [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]] · [[train.py как центр обучения]] · [[Dataset]]
