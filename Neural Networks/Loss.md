---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - learning
confidence: 0.98
---

# Loss

## Простое объяснение
Loss — это оценка учителя: ответ хороший или плохой.

## Зачем это нужно
Без Loss модель не знает, насколько сильно она ошиблась.

## Как это работает
После [[Forward Pass]] модель получает [[Output]]. Loss сравнивает output с правильным target и превращает ошибку в число, от которого начинается [[Backpropagation]].

## Пример
Prediction = 7, Target = 10, Loss = 3.

## Типичные ошибки
- Думать, что Loss исправляет модель.
- Путать Loss и Gradient.

## Вопросы для проверки
- Что показывает Loss?
- Что Loss НЕ умеет делать?

## Следующие темы
- [[Backpropagation]]

## Связанные темы
[[Output]] · [[Backpropagation]] · [[Gradient]]
