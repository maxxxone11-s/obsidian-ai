---
type: concept
area: PyTorch
status: learned
created: 2026-06-27
updated: 2026-06-30
tags:
  - pytorch
  - dataloader
  - batching
confidence: 0.97
difficulty: medium
---

# DataLoader

Stub-заметка для PyTorch DataLoader.

## Простое объяснение

DataLoader берет отдельные элементы из [[Dataset]] и собирает из них batch, который затем передается модели.

## Зачем это нужно

- Делает batching.
- Может перемешивать данные.
- Упрощает цикл обучения.
- Стандартизирует интерфейс между Dataset и Model.

## Как это работает

DataLoader не хранит данные самостоятельно. При каждой итерации он вызывает Dataset, получает отдельные объекты и формирует batch Tensor, обычно в формате `(batch_x, batch_y)`. `train.py` не обязан знать, откуда именно пришли данные.

## Пример

```python
from torch.utils.data import DataLoader

loader = DataLoader(dataset, batch_size=32, shuffle=True)

for x, y in loader:
    pass
```

## Типичные ошибки

- Путать batch size и количество features.
- Не проверять shape batch.
- Забывать `shuffle=True` для train loader.
- Связывать модель с конкретным источником данных.
- Считать DataLoader отдельным хранилищем данных.
- Думать, что DataLoader объединяет весь Dataset в один Tensor.

## Вопросы для проверки

- Что получает DataLoader от Dataset?
- Что DataLoader передает в training loop?
- Почему DataLoader помогает отделить данные от модели?
- Что возвращает `train_loader`?

## Следующие темы

- [[Интерфейс Dataset DataLoader Model]]
- Custom Dataset
- Collate Function

## Связанные темы

- [[Dataset]] · [[Tensor]] · [[Shape]] · [[nn.Module]] · [[Neural Networks/Batch|Batch]] · [[PyTorch Training Loop]] · [[Интерфейс Dataset DataLoader Model]]
