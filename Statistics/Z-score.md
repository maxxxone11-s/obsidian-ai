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
  - Standard Score
  - z
---

# Z-score

## Кратко

Z-score показывает расстояние конкретного значения до среднего в единицах стандартного отклонения.

## Простое объяснение

Z-score показывает, насколько далеко значение находится от среднего относительно распределения данных.

## Зачем это нужно

Z-score позволяет сравнивать признаки с разными единицами измерения и искать выбросы.

## Как это работает

Из значения вычитается [[Mean]], а результат делится на [[Standard Deviation]].

## Пример

```text
Mean = 170
Std = 5
Рост = 180

z = 2
```

## Типичные ошибки

- Считать, что z-score измеряется в исходных единицах.
- Путать z-score со [[Statistics/Standardization|Standardization]] как процессом.

## Вопросы для проверки

- Что означает `z = 0`?
- Что означает `z = -2`?
- Что означает `z = 2`?

## Следующие темы

- Outlier Detection

## Связанные темы

- [[Statistics/Standardization|Standardization]] · [[Standard Deviation]] · [[Normal Distribution]] · [[Machine Learning/Feature Scaling|Feature Scaling]]
