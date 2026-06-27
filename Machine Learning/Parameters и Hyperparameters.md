---
type: concept
area: Machine Learning
status: needs_review
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - optimization
confidence: 0.7
---

# Parameters и Hyperparameters

## Простое объяснение

Weight и Bias — Parameters. Learning Rate — Hyperparameter.

## Зачем это нужно

Это различие встречается практически во всех ML-фреймворках.

## Как это работает

Parameters меняются во время обучения. Hyperparameters задают процесс обучения или структуру модели и выбираются до обучения или через model selection.

## Пример

Weight — модель. Learning Rate — разработчик.

## Типичные ошибки

- Bias сначала был ошибочно отнесен к Hyperparameters.

## Вопросы для проверки

- Кто выбирает Weight?
- Кто выбирает Learning Rate?

## Следующие темы

- [[Grid Search]]

## Связанные темы

- [[Gradient Descent]]
