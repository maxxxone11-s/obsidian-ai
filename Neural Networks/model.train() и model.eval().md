---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - neural-networks
  - pytorch-preview
confidence: 0.98
difficulty: medium
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
- `eval()` не отключает градиенты; для этого нужен [[torch.no_grad()]].
- На простых моделях из Linear и ReLU разницы может почти не быть.

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
- Думать, что `eval()` отключает `backward()`.
- Путать `eval()` и `no_grad()`.

## Вопросы для проверки

- Чем отличаются train() и eval()?
- Когда используется `train()`?
- Когда используется `eval()`?
- Почему для простой модели разница почти незаметна?
- Почему `eval()` не отключает градиенты?

## Следующие темы

- [[PyTorch/model.eval()|model.eval()]]
- [[torch.no_grad()]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]

## Связанные темы

- [[Dropout]] · [[Batch Normalization]] · [[Inference]] · [[torch.no_grad()]] · [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]]
