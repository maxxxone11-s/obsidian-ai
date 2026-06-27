---
type: concept
area: Machine Learning
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - machine-learning
  - scaling
  - gradient-descent
  - optimization
confidence: 0.95
---

# Scaling и Gradient Descent

Scaling помогает алгоритмам на основе [[Gradient Descent]] быстрее и стабильнее сходиться.

## Простое объяснение

Когда признаки имеют очень разные масштабы, optimization идёт неровно: один признак может доминировать просто из-за больших чисел.

## Зачем это нужно

Scaling важен для:

- [[Linear Regression]], если используется gradient descent;
- [[Logistic Regression]];
- [[Neural Networks]];
- любых моделей, где параметры обновляются через градиент.

## Как это работает

[[Feature Scaling]] приводит признаки к сопоставимому масштабу. Тогда gradient descent обновляет параметры более сбалансированно и обучение может сходиться быстрее.

## Пример

До scaling один признак может быть `age = 20`, а другой `income = 100000`. Признак с большими числами начинает доминировать в обучении, хотя это не обязательно означает большую важность.

## Типичные ошибки

- Не понимать, почему scaling помогает [[Gradient Descent]].
- Думать, что scaling нужен только для красивых чисел.
- Не масштабировать данные перед обучением нейросети.

## Связанные темы

- [[Feature Scaling]] · [[Gradient Descent]] · [[Linear Regression]] · [[Logistic Regression]] · [[Neural Networks]]
