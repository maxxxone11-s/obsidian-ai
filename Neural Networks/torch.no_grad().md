---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - neural-networks
  - pytorch-preview
confidence: 0.99
difficulty: medium
---

# torch.no_grad()

## Простое объяснение

Если модель только делает prediction, вычислительный граф больше не нужен.

## Зачем это нужно

`torch.no_grad()` отключает построение вычислительного графа, экономит память и ускоряет inference.

## Как это работает

Контекст `torch.no_grad()` говорит PyTorch не строить graph для gradient computation. После этого `backward()` по результату невозможен.

## Пример

```python
with torch.no_grad():
    prediction = model(x)
```

## Типичные ошибки

- Использовать torch.no_grad() во время обучения.
- Считать, что `no_grad()` выключает модель.
- Путать `no_grad()` и `eval()`.

## Вопросы для проверки

- Почему torch.no_grad() ускоряет работу модели?
- Что отключает `no_grad()`?
- Почему inference быстрее?

## Следующие темы

- [[PyTorch/Autograd|PyTorch Autograd]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]

## Связанные темы

- [[Inference]] · [[Gradient]] · [[PyTorch/Autograd|Autograd]] · [[PyTorch/model.eval()|model.eval()]]
