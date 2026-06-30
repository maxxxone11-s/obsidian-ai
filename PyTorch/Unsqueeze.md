---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - pytorch
  - unsqueeze
  - dimensions
  - tensor
confidence: 0.91
difficulty: medium
---

# Unsqueeze

Unsqueeze добавляет новую ось размера `1` в Tensor.

## Простое объяснение

`unsqueeze()` не меняет данные. Он добавляет новый уровень структуры, чтобы Tensor стал совместим с batch processing, channel dimension или [[Broadcasting]].
`unsqueeze(0)` часто добавляет batch dimension к одному объекту.

## Зачем это нужно

- Добавить batch dimension.
- Добавить channel dimension.
- Подготовить Tensor к операции с другим Tensor.
- Подать одно изображение в модель, которая ожидает batch.

## Как это работает

Если был Tensor формы `(5,)`, то:

- `unsqueeze(0)` даст `(1, 5)`;
- `unsqueeze(1)` даст `(5, 1)`.

Для inference это означает: один объект превращается в batch из одного объекта.

## Пример

```python
import torch

x = torch.randn(5)

print(x.unsqueeze(0).shape)  # torch.Size([1, 5])
print(x.unsqueeze(1).shape)  # torch.Size([5, 1])
```

## Типичные ошибки

- Неправильно выбирать позицию новой оси.
- Путать `unsqueeze(0)` и `unsqueeze(-1)`.
- Забывать, что данные не меняются, меняется только shape.
- Передавать Tensor в модель без batch dimension.

## Вопросы для проверки

- Почему нужен batch из одного элемента?
- Что меняется после `unsqueeze(0)`?
- Меняются ли сами данные?

## Следующие темы

- [[preprocess_image()]]

## Связанные темы

- [[Tensor]] · [[Shape]] · [[Reshape]] · [[View]] · [[Squeeze]] · [[Broadcasting]] · [[preprocess_image()]]
