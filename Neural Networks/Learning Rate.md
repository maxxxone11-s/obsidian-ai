---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - machine-learning
  - mathematics
  - optimization
  - neural-networks
  - learning
confidence: 0.95
---

# Learning Rate

## Кратко

Learning Rate — размер шага обучения.

## Простое объяснение

Маленький шаг — долго идти. Большой шаг — можно перепрыгнуть минимум.

Насколько сильно менять веса за один шаг.

## Зачем это нужно

От Learning Rate зависит скорость и стабильность обучения.

Слишком большой шаг приводит к перескоку минимума.

## Как это работает

Optimizer умножает Gradient на learning rate и применяет update к параметрам. Слишком большой шаг делает обучение нестабильным, слишком маленький — медленным.

Learning Rate масштабирует градиент перед обновлением параметров.

## Пример

`lr = 0.001`.

`lr = 0.01`.

## Типичные ошибки

- Считать большой Learning Rate всегда лучшим.

## Вопросы для проверки

- Что произойдет при слишком большом Learning Rate?
- Что произойдет при слишком маленьком?

## Следующие темы

- [[Adam]]

- [[Machine Learning/Loss Function|Loss Function]]

## Связанные темы

- [[Machine Learning/Gradient Descent|Gradient Descent]] · [[Optimizer]]

- [[Machine Learning/Gradient Descent|Gradient Descent]]
