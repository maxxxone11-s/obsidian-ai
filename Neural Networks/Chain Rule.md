---
type: concept
area: Neural Networks
status: needs_review
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - learning
confidence: 0.75
---

# Chain Rule

## Простое объяснение

Weight не влияет на Loss напрямую. Он влияет через множество промежуточных вычислений, а Chain Rule объединяет всю цепочку.

## Зачем это нужно

Именно благодаря Chain Rule работает Backpropagation.

## Как это работает

Если параметр влияет на скрытый слой, скрытый слой влияет на output, а output влияет на loss, Chain Rule перемножает эти локальные влияния в общий градиент.

## Пример

Weight → Hidden Layer → Output → Loss.

## Типичные ошибки

- Представлять влияние Weight как прямое.

## Вопросы для проверки

- Почему нужен Chain Rule?

## Следующие темы

- [[Optimizer]]

## Связанные темы

- [[Gradient]] · [[Backpropagation]]
