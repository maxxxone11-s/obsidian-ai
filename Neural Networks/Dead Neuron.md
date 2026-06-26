---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - activation-functions
confidence: 0.9
---

# Dead Neuron

## Простое объяснение
Нейрон перестает передавать сигнал и фактически выключается.

## Зачем это нужно
Это один из недостатков ReLU.

## Как это работает
Если ReLU всё время получает отрицательный [[Score]], её output равен 0, а градиент может не проходить дальше.

## Пример
Output = 0 всегда.

## Типичные ошибки
- Думать, что Dead Neuron нельзя избежать.

## Вопросы для проверки
- Почему возникает Dead Neuron?

## Следующие темы
- [[Leaky ReLU]]

## Связанные темы
[[ReLU]] · [[Leaky ReLU]]
