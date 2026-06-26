---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - regularization
confidence: 0.95
---

# Batch Normalization

## Простое объяснение
Каждый следующий слой получает данные примерно одинакового масштаба, поэтому ему легче обучаться.

## Зачем это нужно
BatchNorm делает обучение стабильнее, быстрее и позволяет использовать больший Learning Rate.

## Как это работает
BatchNorm считает статистики по batch и нормализует внутренние активации слоя. Это не то же самое, что [[Scaling]] входных features.

## Пример
До: [150, 220, 300]. После: [-1.0, 0.2, 1.4].

## Типичные ошибки
- Путать BatchNorm и Feature Scaling.

## Вопросы для проверки
- Что делает BatchNorm?
- Почему он ускоряет обучение?

## Следующие темы
- [[Train Validation Test]]

## Связанные темы
[[Batch]] · [[Scaling]] · [[Dropout]]
