---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - ml-engineering
  - model
confidence: 0.99
difficulty: medium
---

# model.py как отдельная ответственность

## Простое объяснение

`model.py` отвечает исключительно за построение вычислений, которые выполняются при вызове `model(x)`.

## Зачем это нужно

Архитектура модели должна быть независима от обучения и источника данных. Так одну и ту же архитектуру можно использовать в training, validation и inference.

## Как это работает

Внутри обычно находятся:

- класс модели;
- слои;
- `forward()`.

Внутри не должны находиться Dataset, DataLoader, optimizer, loss или training loop.

## Пример

```python
class NeuralNet(nn.Module):
    ...
```

## Типичные ошибки

- Добавлять optimizer внутрь модели.
- Добавлять Dataset внутрь модели.
- Добавлять DataLoader внутрь модели.
- Загружать данные внутри `model.py`.

## Вопросы для проверки

- Что должно находиться внутри `model.py`?
- Почему optimizer не относится к `model.py`?
- Почему `model.py` не знает ничего о Dataset?
- Что происходит при вызове `model(x)`?

## Следующие темы

- [[predict.py]]

## Связанные темы

- [[nn.Module]] · [[train.py как центр обучения]] · [[predict.py]] · [[Архитектура ML-проекта]]
