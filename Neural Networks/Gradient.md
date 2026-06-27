---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - learning
confidence: 0.97
---

# Gradient

## Кратко

Gradient — результат работы Backpropagation. Он показывает, как каждый Weight и Bias влияют на Loss.

## Простое объяснение

Stub-заметка для связанной темы из импорта [[Feature]] и [[Activation Function]].

Представь тысячи ручек. Gradient говорит, какую крутить, насколько и в какую сторону.

## Зачем это нужно

Эта тема помогает связать фундамент нейросетей с обучением модели и forward/backward pass.

Optimizer использует именно Gradient для обновления параметров модели.

## Как это работает

Пока не раскрыто.

Backpropagation вычисляет производные Loss по параметрам модели. Эти производные вместе образуют Gradient, который передаётся в [[Optimizer]].

## Пример

Пока не добавлен.

`dLoss/dw1`, `dLoss/db1`.

## Типичные ошибки

- Пока не добавлены.

- Путать Gradient и Loss.
- Думать, что Gradient меняет веса.

## Вопросы для проверки

- Что содержит Gradient?
- Чем он отличается от Loss?

## Следующие темы

- [[Machine Learning/Gradient Descent|Gradient Descent]]

## Связанные темы

- [[Feature]] · [[Activation Function]] · [[Model]]

- [[Backpropagation]] · [[Optimizer]] · [[Machine Learning/Gradient Descent|Gradient Descent]]
