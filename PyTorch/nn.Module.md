---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - pytorch
  - model
  - architecture
confidence: 0.99
difficulty: medium
---

# nn.Module

## Простое объяснение

`nn.Module` — базовый класс PyTorch для описания модели. `__init__` строит модель, а `forward` описывает движение данных через уже созданные слои.

## Зачем это нужно

Практически все проекты на PyTorch строят модели через наследование от `nn.Module`.
Это позволяет использовать одну и ту же архитектуру в обучении, валидации и inference.

## Как это работает

- `__init__` создает слои.
- `forward` описывает вычисления.
- `model(x)` автоматически вызывает `forward()`.
- Внутри `nn.Module` могут быть слои вроде [[nn.Linear]].
- В реальном проекте класс модели обычно лежит в [[model.py как отдельная ответственность|model.py]].

## Пример

```python
from torch import nn

class MyModel(nn.Module):
    def __init__(self):
        super().__init__()
        self.l1 = nn.Linear(3, 5)

    def forward(self, x):
        return self.l1(x)
```

## Типичные ошибки

- Путать `nn.Module` как базовый класс модели и [[nn.Linear]] как конкретный слой.
- Путать работу `__init__` и `forward`.
- Считать, что `__init__` вызывается при каждом prediction.
- Добавлять optimizer или Dataset внутрь модели.

## Вопросы для проверки

- Что создается в `__init__`?
- Что делает `forward()`?
- Почему вызывают `model(x)`, а не `model.forward(x)`?
- Почему optimizer не относится к `model.py`?

## Следующие темы

- [[model.py как отдельная ответственность]]

## Связанные темы

- [[Neural Networks/Forward Pass|Forward Pass]] · [[Neural Networks/Optimizer|Optimizer]] · [[Neural Networks/Inference|Inference]] · [[nn.Linear]] · [[PyTorch Training Loop]] · [[model.py как отдельная ответственность]]

## Связь с Tensor Fundamentals

[[nn.Module]] получает на вход [[Tensor]], ожидает корректный [[Shape]] и обычно используется вместе с [[Dataset]] и [[DataLoader]].
