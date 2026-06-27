---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - neural-networks
  - pytorch-preview
confidence: 0.92
---

# model.train() и model.eval()

## Простое объяснение

model.train() включает режим обучения. model.eval() включает режим использования модели.

## Зачем это нужно

Dropout и BatchNorm работают по-разному в этих режимах.

## Как это работает

В режиме train активны training-особенности вроде [[Dropout]]. В режиме eval модель ведёт себя как на [[Inference]]: Dropout отключён, а [[Batch Normalization]] использует накопленную статистику.

## Пример

model.train() → Dropout включен. model.eval() → Dropout выключен.

## Типичные ошибки

- Забывать переключать режим модели.

## Вопросы для проверки

- Чем отличаются train() и eval()?

## Следующие темы

- [[PyTorch/Index|PyTorch]]

## Связанные темы

- [[Dropout]] · [[Batch Normalization]] · [[Inference]]
