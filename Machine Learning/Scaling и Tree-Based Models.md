---
type: concept
area: Machine Learning
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - machine-learning
  - scaling
  - decision-tree
  - tree-based-models
confidence: 0.95
---

# Scaling и Tree-Based Models

Деревьям решений scaling почти не нужен.

## Простое объяснение

[[Decision Tree]] принимает решения через пороги вида `feature <= value`. Для дерева важен порядок значений, а не их абсолютный масштаб.

## Зачем это нужно

Это помогает не усложнять preprocessing там, где scaling не критичен:

- [[Decision Tree]];
- [[Random Forest]];
- [[XGBoost]].

## Как это работает

Порог просто сдвинется, но логика останется той же:

```text
До scaling:          После scaling:
age <= 30?           age <= 0.5?
     |                    |
   Yes  No             Yes  No
```

## Пример

Если дерево делило данные по `age <= 30`, после scaling оно может делить по `age <= 0.5`. Относительный порядок объектов сохраняется.

## Типичные ошибки

- Думать, что scaling обязателен для всех моделей.
- Не понимать, почему деревьям scaling не нужен.
- Путать tree-based models с distance-based models.

## Связанные темы

- [[Feature Scaling]] · [[Decision Tree]] · [[Random Forest]] · [[XGBoost]] · [[Scaling для KNN и SVM]]
