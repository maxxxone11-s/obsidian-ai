---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - pytorch
  - inference
  - model-mode
confidence: 0.93
difficulty: easy
---

# model.eval()

## Простое объяснение

`model.eval()` переводит модель в режим валидации или инференса. Он не запускает prediction сам по себе.

## Зачем это нужно

Некоторые слои работают по-разному в train/eval режимах. Поэтому перед validation, test и inference нужно явно переключать модель.

## Как это работает

- `model.train()` включает режим обучения.
- `model.eval()` включает режим инференса.
- Для простой модели разница может быть почти незаметна.
- Для моделей с [[Neural Networks/Dropout|Dropout]] или [[Neural Networks/Batch Normalization|Batch Normalization]] режим критически важен.

## Пример

```python
model.eval()
prediction = model(x)
```

## Типичные ошибки

- Пытаться вызвать `model.eval(x)`.
- Думать, что `eval()` делает prediction.
- Забывать переключать модель перед validation.

## Вопросы для проверки

- Когда используется `model.eval()`?
- Почему `eval()` не заменяет `model(x)`?
- Какие слои чувствительны к train/eval режиму?

## Следующие темы

- [[torch.no_grad()]]

## Связанные темы

- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] · [[Neural Networks/Inference|Inference]] · [[PyTorch Training Loop]]
