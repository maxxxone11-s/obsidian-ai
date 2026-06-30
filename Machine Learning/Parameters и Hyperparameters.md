---
type: concept
area: Machine Learning
status: needs_review
created: 2026-06-26
updated: 2026-06-30
tags:
  - machine-learning
  - optimization
confidence: 0.7
difficulty: medium
---

# Parameters и Hyperparameters

## Простое объяснение

Weight и Bias — Parameters. Learning Rate — Hyperparameter.
Но не все значения в `config.py` являются гиперпараметрами: часть параметров определяется самим датасетом.

## Зачем это нужно

Это различие встречается практически во всех ML-фреймворках.

## Как это работает

Parameters меняются во время обучения. Hyperparameters задают процесс обучения или структуру модели и выбираются до обучения или через model selection.

В PyTorch-проектах важно отделять гиперпараметры от параметров датасета:

- `learning_rate`, `batch_size`, `epochs`, `hidden_size` выбирает инженер;
- `input_size` и `num_classes` определяются данными.

## Пример

```text
weight, bias -> parameters
learning_rate, hidden_size -> hyperparameters
input_size, num_classes -> параметры датасета
```

## Типичные ошибки

- Bias сначала был ошибочно отнесен к Hyperparameters.
- Считать `input_size` гиперпараметром.
- Считать `num_classes` гиперпараметром.

## Вопросы для проверки

- Кто выбирает Weight?
- Кто выбирает Learning Rate?
- Какие параметры задаются датасетом?
- Почему `input_size` нельзя выбирать произвольно?

## Следующие темы

- [[PyTorch/config.py|config.py]]
- [[Grid Search]]

## Связанные темы

- [[Gradient Descent]] · [[PyTorch/config.py|config.py]] · [[PyTorch/Dataset|Dataset]]
