---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - activation-functions
confidence: 0.88
---

# Tanh

## Простое объяснение

Tanh позволяет работать с отрицательными значениями.

## Зачем это нужно

Исторически использовалась вместо Sigmoid во многих архитектурах.

## Как это работает

Tanh похожа на Sigmoid, но центрирована около нуля: отрицательные входы дают отрицательный output, положительные — положительный.

## Пример

Если score = 0, output = 0.

## Типичные ошибки

- Путать диапазон Tanh и Sigmoid.

## Вопросы для проверки

- Чем Tanh отличается от Sigmoid?

## Следующие темы

- [[ReLU]]

## Связанные темы

- [[Sigmoid]] · [[ReLU]]
