---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - optimizers
confidence: 0.92
---

# Momentum

## Простое объяснение
Вместо того чтобы смотреть только на текущий Gradient, модель учитывает, куда двигалась раньше.

## Зачем это нужно
Уменьшает колебания и ускоряет обучение.

## Как это работает
Momentum хранит сглаженное направление прошлых updates и добавляет его к текущему шагу [[Optimizer]].

## Пример
Без Momentum: ← → ← →. С Momentum: →→→.

## Типичные ошибки
- Думать, что Momentum хранит прошлый Gradient полностью.

## Вопросы для проверки
- Почему Momentum ускоряет обучение?

## Следующие темы
- [[Adam]]

## Связанные темы
[[SGD]] · [[Adam]]
