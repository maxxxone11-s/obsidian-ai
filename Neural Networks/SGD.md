---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - optimizers
confidence: 0.95
---

# Stochastic Gradient Descent (SGD)

## Простое объяснение

Одно изображение — один Gradient — одно обновление.

## Зачем это нужно

Позволяет обучаться быстрее, но делает обучение шумным.

## Как это работает

Вместо всего датасета SGD берёт один пример, считает [[Loss]], [[Gradient]] и сразу обновляет параметры.

## Пример

Image → Gradient → Update.

## Типичные ошибки

- Думать, что SGD всегда хуже Adam.

## Вопросы для проверки

- Почему SGD нестабилен?

## Следующие темы

- [[Momentum]]

## Связанные темы

- [[Batch Gradient Descent]] · [[Mini-Batch Gradient Descent]] · [[Momentum]]
