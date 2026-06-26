---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - optimizers
confidence: 0.99
---

# Mini-Batch Gradient Descent

## Простое объяснение
Это компромисс между скоростью, памятью и качеством обучения.

## Зачем это нужно
Практически все современные модели обучаются именно так.

## Как это работает
Данные делятся на [[Batch]]. Для каждого batch считается средний [[Gradient]], после чего [[Optimizer]] делает step.

## Пример
Batch = 32 → средний Gradient → Optimizer Step.

## Типичные ошибки
- Путать Batch и Epoch.

## Вопросы для проверки
- Почему Mini-Batch считается золотой серединой?

## Следующие темы
- [[Batch]]

## Связанные темы
[[Batch]] · [[Epoch]] · [[SGD]]
