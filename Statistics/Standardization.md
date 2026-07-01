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
  - Z-score Standardization
  - Feature Standardization
---

# Standardization

## Кратко

Standardization преобразует данные так, чтобы среднее стало 0, а стандартное отклонение - 1.

## Простое объяснение

Все признаки переводятся в единый статистический масштаб.

## Зачем это нужно

Standardization - один из самых популярных способов подготовки данных для ML.

## Как это работает

Для каждого значения вычитается [[Mean]], а результат делится на [[Standard Deviation]].

## Пример

```text
После стандартизации:
Mean = 0
Standard Deviation = 1
```

## Типичные ошибки

- Называть Standardization "Normalization".
- Путать с [[Min-Max Normalization]].
- Путать z-score как значение и Standardization как процесс.

## Вопросы для проверки

- Какими становятся Mean и Standard Deviation после стандартизации?

## Следующие темы

- [[Normal Distribution]]

## Связанные темы

- [[Z-score]] · [[Mean]] · [[Standard Deviation]] · [[Machine Learning/Standardization|Standardization в Machine Learning]]
