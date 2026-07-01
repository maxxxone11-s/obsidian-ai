---
type: concept
area: Statistics
knowledge_area: Statistics
status: learned
created: 2026-07-01
updated: 2026-07-01
tags:
  - statistics
confidence: high
difficulty: beginner
aliases:
  - Min-Max Scaling
  - Normalization
---

# Min-Max Normalization

## Кратко

Min-Max Normalization масштабирует значения в диапазон от 0 до 1.

## Простое объяснение

Все данные приводятся к одному диапазону.

## Зачем это нужно

Min-Max Normalization позволяет признакам одинаково участвовать в обучении модели.

## Как это работает

```text
x' = (x - min(x)) / (max(x) - min(x))
```

Где:

- `x` — исходное значение.
- `x'` — нормализованное значение.
- `min(x)` — минимальное значение признака.
- `max(x)` — максимальное значение признака.

## Пример

```text
[10, 20, 30, 40, 50]
→
[0, 0.25, 0.5, 0.75, 1]
```

## Типичные ошибки

- Путать с [[Statistics/Standardization|Standardization]].
- Не учитывать влияние выбросов.

## Вопросы для проверки

- Какое значение всегда получает минимальный элемент?
- Какое значение всегда получает максимальный элемент?

## Следующие темы

- [[Statistics/Standardization|Standardization]]

## Связанные темы

- [[Statistics/Standardization|Standardization]] · [[Machine Learning/Normalization|Normalization]] · [[Machine Learning/Feature Scaling|Feature Scaling]]
