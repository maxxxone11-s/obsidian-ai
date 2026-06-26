---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - activation-functions
confidence: 0.94
---

# Score

## Простое объяснение
Score — это сырая оценка нейрона.

## Зачем это нужно
Все функции активации работают именно со Score.

## Как это работает
Нейрон складывает взвешенные признаки и bias: `score = Σ(feature × weight) + bias`. Затем [[Activation Function]] преобразует Score в [[Output]].

## Пример
`score = Σ(feature × weight) + bias`

## Типичные ошибки
- Путать Score с Output.

## Вопросы для проверки
- Что такое Score?
- Почему это еще не ответ модели?

## Следующие темы
- [[Sigmoid]]
- [[ReLU]]

## Связанные темы
[[Activation Function]] · [[Sigmoid]] · [[ReLU]] · [[Softmax]]
