---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - inference
  - image-preprocessing
confidence: 0.98
difficulty: medium
---

# preprocess_image()

## Простое объяснение

`preprocess_image()` подготавливает изображение для подачи в нейронную сеть.

## Зачем это нужно

Модель ожидает Tensor фиксированной формы, а исходное изображение обычно нужно открыть, привести к RGB, преобразовать и добавить batch dimension.

## Как это работает

```text
Image.open()
↓
convert("RGB")
↓
transforms
↓
ToTensor()
↓
unsqueeze(0)
↓
to(device)
```

## Пример

```python
tensor = tensor.unsqueeze(0)
```

## Типичные ошибки

- Передавать изображение без batch dimension.
- Думать, что `convert("RGB")` превращает изображение в Tensor.

## Вопросы для проверки

- Почему используется `unsqueeze(0)`?
- Зачем нужен `convert("RGB")`?

## Следующие темы

- torchvision.transforms

## Связанные темы

- [[Unsqueeze]] · [[Tensor]] · [[Shape]] · [[Inference Pipeline]]
