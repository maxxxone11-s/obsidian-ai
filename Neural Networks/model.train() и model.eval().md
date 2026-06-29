---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - neural-networks
  - pytorch-preview
confidence: 0.93
difficulty: easy
---

# model.train() и model.eval()

## Простое объяснение

`model.train()` включает режим обучения. `model.eval()` включает режим валидации и инференса.

## Зачем это нужно

Некоторые слои, например [[Dropout]] и [[Batch Normalization]], работают по-разному во время обучения и предсказаний.

## Как это работает

- Перед обучением вызывается `model.train()`.
- Перед валидацией и инференсом вызывается `model.eval()`.
- `eval()` не делает prediction сам по себе, а только переключает режим модели.

## Пример

```python
model.train()
# training loop

model.eval()
# validation или inference
```

## Типичные ошибки

- Забывать переключать режим модели.
- Пытаться вызвать `model.eval(x)`.
- Думать, что `eval()` сам выполняет prediction.

## Вопросы для проверки

- Чем отличаются train() и eval()?
- Когда используется `train()`?
- Когда используется `eval()`?
- Почему для простой модели разница почти незаметна?

## Следующие темы

- [[PyTorch/model.eval()|model.eval()]]
- [[torch.no_grad()]]

## Связанные темы

- [[Dropout]] · [[Batch Normalization]] · [[Inference]] · [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]]
