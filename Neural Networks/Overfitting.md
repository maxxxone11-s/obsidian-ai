---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - regularization
confidence: 0.98
---

# Overfitting

## Простое объяснение

Модель выучила ответы, но не научилась думать.

## Зачем это нужно

Overfitting — главная проблема обучения нейросетей.

## Как это работает

Модель слишком хорошо подстраивается под [[Train Set]], поэтому качество на [[Validation]] или [[Test Set]] становится хуже.

## Пример

Train Accuracy = 99%, Test Accuracy = 72%.

## Типичные ошибки

- Считать, что высокая Accuracy всегда означает хорошую модель.

## Вопросы для проверки

- Почему возникает Overfitting?

## Следующие темы

- [[Dropout]]

## Связанные темы

- [[Dropout]] · [[Validation]] · [[Test Set]]
