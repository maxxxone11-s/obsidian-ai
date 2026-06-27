---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - activation-functions
confidence: 0.98
---

# ReLU

## Простое объяснение

Если сигнал полезный — пропускаем. Если отрицательный — выключаем.

## Зачем это нужно

Сегодня ReLU является стандартной функцией активации для скрытых слоёв.

## Как это работает

ReLU вычисляет `max(0, score)`. Она проста, быстра и уменьшает проблему vanishing gradient для положительных значений.

## Пример

`output = max(0, score)`

## Типичные ошибки

- Думать, что ReLU нормализует положительные значения.

## Вопросы для проверки

- Почему ReLU стала стандартом?

## Следующие темы

- [[Dead Neuron]]
- [[Leaky ReLU]]

## Связанные темы

- [[Leaky ReLU]] · [[Dead Neuron]] · [[Vanishing Gradient]]
