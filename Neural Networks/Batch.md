---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - training
confidence: 0.98
---

# Batch

## Кратко

Batch — небольшая часть Train Set, которая используется за один цикл обучения.

## Простое объяснение

Stub-заметка для следующего шага после импорта [[Forward Pass]] и [[Backpropagation]].

Вместо всего датасета модель берет маленькую пачку данных.

## Зачем это нужно

Эта тема нужна для понимания организации цикла обучения нейросети.

После каждого Batch происходит обновление параметров.

## Как это работает

Пока не раскрыто.

Один [[Epoch]] состоит из нескольких batch. На каждом batch модель выполняет [[Forward Pass]], считает [[Loss]], делает [[Backpropagation]] и обновляет параметры.

## Пример

Пока не добавлен.

Dataset = 1000 изображений, Batch Size = 100, получаем 10 Batch.

## Типичные ошибки

- Пока не добавлены.

- Путать Batch и Epoch.

## Вопросы для проверки

- Когда обновляются Weight?

## Следующие темы

- [[Epoch]]

## Связанные темы

- [[Forward Pass]] · [[Loss]] · [[Optimizer]]

- [[Epoch]] · [[Mini-Batch Gradient Descent]]
