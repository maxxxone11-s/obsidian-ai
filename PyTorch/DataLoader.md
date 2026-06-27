---
type: concept
area: PyTorch
status: draft
created: 2026-06-27
updated: 2026-06-27
tags:
  - pytorch
  - dataloader
  - batching
confidence: 0
---

# DataLoader

Stub-заметка для PyTorch DataLoader.

## Простое объяснение

DataLoader берёт данные из [[Dataset]] и собирает их в batch для обучения модели.

## Зачем это нужно

- Делает batching.
- Может перемешивать данные.
- Упрощает цикл обучения.

## Как это работает

DataLoader итерируется по Dataset и возвращает batch Tensor.

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

## Связанные темы

[[Dataset]] · [[Tensor]] · [[Shape]] · [[nn.Module]]
