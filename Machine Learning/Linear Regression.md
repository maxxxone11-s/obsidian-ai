---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-07-11
tags:
  - machine-learning
  - algorithm
  - regression
  - linear-model
confidence: 0.95
---

# Linear Regression

## Кратко

Linear Regression — линейная модель y = wx + b. Модель ищет такие веса, чтобы минимизировать ошибку.

## Простое объяснение

Каждый Feature умножается на свой вес, затем добавляется bias, и модель получает числовой прогноз.

## Зачем это нужно

Linear Regression помогает понять базовую идею обучения модели и служит мостом к нейронным сетям.

## Как это работает

Модель использует формулу `y = wx + b`, сравнивает прогноз с правильным ответом через [[Loss Function]] и подбирает веса так, чтобы ошибка уменьшалась.

## Пример

`y = wx + b` для прогноза цены квартиры по площади.

## Типичные ошибки

- Путать Weight и Bias.

- Думать, что Regression и Linear Regression — одно и то же.

## Вопросы для проверки

- Что такое Weight?
- Что такое Bias?

## Следующие темы

- [[Loss Function]]

## Связанные темы

- [[Regression]] · [[Gradient Descent]] · [[Loss Function]]
