---
type: concept
area: Statistics
knowledge_area: Statistics
status: learned
created: 2026-07-01
updated: 2026-07-11
tags: [statistics, standardization, z-score]
confidence: high
difficulty: beginner
aliases: [Standardization, Z-score Standardization, Statistical Standardization, Стандартизация по z-score]
---

# Z-score Standardization

## Академическое определение

Z-score Standardization — преобразование числовой переменной по формуле \(z = (x - \mu) / \sigma\), после которого её среднее становится 0, а стандартное отклонение — 1.

## Инженерное назначение

Преобразование переводит величины в единый статистический масштаб и позволяет интерпретировать значение через число стандартных отклонений от среднего.

## Причина существования

Признаки и наблюдения могут иметь несопоставимые центры и масштабы. Без стандартизации абсолютная величина одной переменной может доминировать над другими только из-за единиц измерения.

## Простое объяснение

Из каждого значения вычитается среднее, после чего результат делится на стандартное отклонение. Ноль соответствует среднему, а единица — одному стандартному отклонению.

## Как это работает

1. Вычисляется [[Statistics/Mean|Mean]] \(\mu\).
2. Вычисляется [[Statistics/Standard Deviation|Standard Deviation]] \(\sigma\).
3. Для каждого значения применяется `z = (x - μ) / σ`.
4. Полученное распределение имеет `μ' = 0` и `σ' = 1`.

## Пример

Если `x` находится на одно стандартное отклонение выше среднего, после преобразования его z-score будет равен `1`.

## Типичные ошибки

- Называть Standardization Min-Max Normalization.
- Путать [[Statistics/Z-score|Z-score]] как отдельное значение и Standardization как процесс преобразования набора данных.
- Считать, что стандартизация обязательно создаёт Normal Distribution.

## Связанные темы

[[Statistics/Z-score|Z-score]] · [[Statistics/Mean|Mean]] · [[Statistics/Standard Deviation|Standard Deviation]] · [[Statistics/Min-Max Normalization|Min-Max Normalization]] · [[Machine Learning/Feature Standardization|Feature Standardization]]

## Вопросы для проверки

- Какими становятся Mean и Standard Deviation после стандартизации?
- Что показывает стандартизированное значение `z = 1`?
- Чем Standardization отличается от Min-Max Normalization?

## Следующие темы

[[Statistics/Z-score|Z-score]] · [[Statistics/Normal Distribution|Normal Distribution]] · [[Machine Learning/Feature Standardization|Feature Standardization]]
