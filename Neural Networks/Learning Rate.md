---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - machine-learning
  - mathematics
  - optimization
  - neural-networks
  - learning
confidence: 0.95
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

## Импорт KNOWLEDGE_EXPORT — 2026-06-26

**Кратко:** Learning Rate — размер шага обучения.

**Простое объяснение:** Насколько сильно менять веса за один шаг.

**Зачем это нужно:** Слишком большой шаг приводит к перескоку минимума.

**Как это работает:** Learning Rate масштабирует градиент перед обновлением параметров.

**Пример:** `lr = 0.01`.

**Типичные ошибки:**
- Пока не замечены.

**Вопросы для проверки:**
- Что произойдет при слишком большом Learning Rate?

**Следующие темы:**
- [[Machine Learning/Loss Function|Loss Function]]

**Связанные темы:** [[Machine Learning/Gradient Descent|Gradient Descent]]
