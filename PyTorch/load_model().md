---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - inference
  - model-loading
confidence: 0.99
difficulty: medium
---

# load_model()

## Простое объяснение

`load_model()` создает архитектуру, загружает обученные веса, переносит модель на устройство и переводит ее в `eval()`.

## Зачем это нужно

Без загрузки весов модель будет содержать случайные параметры и не сможет использовать результат обучения.

## Как это работает

1. Создать модель.
2. Вызвать `torch.load()`.
3. Вызвать `load_state_dict()`.
4. Перенести модель через `model.to(device)`.
5. Вызвать `model.eval()`.

## Пример

```python
model.load_state_dict(torch.load(path))
model.eval()
```

## Типичные ошибки

- Забывать `model.eval()`.
- Пытаться загрузить веса без создания архитектуры.

## Вопросы для проверки

- Почему сначала создается модель?
- Что делает `load_state_dict()`?

## Следующие темы

- State Dict

## Связанные темы

- [[predict.py]] · [[Inference Pipeline]] · [[PyTorch/model.eval()|model.eval()]] · [[model.py как отдельная ответственность]]
