---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - learning
confidence: 0.97
---

# Learning Rate

## Простое объяснение
Маленький шаг — долго идти. Большой шаг — можно перепрыгнуть минимум.

## Зачем это нужно
От Learning Rate зависит скорость и стабильность обучения.

## Как это работает
Optimizer умножает Gradient на learning rate и применяет update к параметрам. Слишком большой шаг делает обучение нестабильным, слишком маленький — медленным.

## Пример
`lr = 0.001`.

## Типичные ошибки
- Считать большой Learning Rate всегда лучшим.

## Вопросы для проверки
- Что произойдет при слишком большом Learning Rate?
- Что произойдет при слишком маленьком?

## Следующие темы
- [[Adam]]

## Связанные темы
[[Machine Learning/Gradient Descent|Gradient Descent]] · [[Optimizer]]
