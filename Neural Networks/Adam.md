---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - optimizers
confidence: 0.88
---

# Adam

## Кратко

Adam объединяет Momentum и адаптивный Learning Rate.

## Простое объяснение

Stub-заметка для связанной темы из импорта [[Forward Pass]] и [[Backpropagation]].

Adam понимает, что каждому Weight нужен свой размер шага.

## Зачем это нужно

Эта тема помогает понять полный цикл обучения нейросети.

Сегодня является самым популярным оптимизатором общего назначения.

## Как это работает

Пока не раскрыто.

Adam хранит сглаженное направление градиента и оценку масштаба градиентов, поэтому может выбирать индивидуальный [[Learning Rate]] для разных параметров.

## Пример

Пока не добавлен.

Weight 1: lr маленький. Weight 2: lr большой.

## Типичные ошибки

- Пока не добавлены.

- Думать, что Adam вычисляет Gradient.
- Не понимать, откуда берется индивидуальный Learning Rate.

## Вопросы для проверки

- Почему Adam лучше обычного SGD?
- Что он хранит кроме Gradient?

## Следующие темы

- [[Regularization]]

## Связанные темы

- [[Forward Pass]] · [[Backpropagation]] · [[Gradient]]

- [[Momentum]] · [[Learning Rate]] · [[Optimizer]]
