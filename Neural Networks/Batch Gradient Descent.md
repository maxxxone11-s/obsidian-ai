---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - optimizers
confidence: 0.94
---

# Batch Gradient Descent

## Простое объяснение
Сначала модель смотрит весь датасет. Потом делает один шаг обучения.

## Зачем это нужно
Исторически это первый вариант Gradient Descent.

## Как это работает
Модель делает [[Forward Pass]] по всему [[Train Set]], считает общий [[Gradient]] и затем [[Optimizer]] выполняет одно обновление параметров.

## Пример
10000 изображений → один Gradient → одно обновление Weight.

## Типичные ошибки
- Считать этот способ самым быстрым.

## Вопросы для проверки
- Почему Batch Gradient Descent редко используют сегодня?

## Следующие темы
- [[Mini-Batch Gradient Descent]]

## Связанные темы
[[SGD]] · [[Mini-Batch Gradient Descent]] · [[Batch]]
