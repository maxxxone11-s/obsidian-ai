---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - machine-learning
  - algorithms
  - algorithm
  - ensemble
  - gradient-boosting
confidence: 0.95
---

# XGBoost

Extreme Gradient Boosting — продвинутый алгоритм ансамбля деревьев. Не требует масштабирования.

## Связанные темы

- [[Feature Scaling]] — не критично для XGBoost
- [[Random Forest]] — похожая идея ансамбля
- [[Decision Tree]] — базовый алгоритм

---

**Статус:** stub, требует полной разработки

## Импорт KNOWLEDGE_EXPORT — Machine Learning Fundamentals — 2026-06-26

**Кратко:** Linear Regression — линейная модель y = wx + b. Модель ищет такие веса, чтобы минимизировать ошибку.

**Простое объяснение:** Каждый Feature умножается на свой вес.

**Зачем это нужно:** На Linear Regression удобно объяснять обучение нейронных сетей.

**Как это работает:** Модель подбирает weight и bias так, чтобы predictions были ближе к правильным labels. Ошибка измеряется через loss, а параметры можно обновлять через gradient descent.

**Пример:** `y = wx + b`.

**Типичные ошибки:**
- Путать Weight и Bias.

**Вопросы для проверки:**
- Что такое Weight?
- Что такое Bias?

**Следующие темы:**
- [[Loss Function]]

**Связанные темы:** [[Gradient Descent]] · [[Loss Function]]
## Простое объяснение
Каждый Feature умножается на свой вес, затем добавляется bias, и модель получает числовой прогноз.

## Зачем это нужно
Linear Regression помогает понять базовую идею обучения модели и служит мостом к нейронным сетям.

## Как это работает
Модель использует формулу `y = wx + b`, сравнивает прогноз с правильным ответом через [[Loss Function]] и подбирает веса так, чтобы ошибка уменьшалась.

## Пример
`y = wx + b` для прогноза цены квартиры по площади.

## Типичные ошибки
- Путать Weight и Bias.
- Думать, что Regression и Linear Regression — одно и то же.

## Связанные темы
[[Regression]] · [[Gradient Descent]] · [[Loss Function]]

