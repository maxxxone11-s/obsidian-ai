---
type: concept
area: PyTorch
status: learned
created: 2026-06-27
updated: 2026-07-11
tags: [pytorch, dataset, data]
aliases: [PyTorch Dataset, torch.utils.data.Dataset, Dataset Interface]
confidence: 0.98
difficulty: medium
---

# PyTorch Dataset

## Академическое определение

PyTorch Dataset — объект, реализующий интерфейс доступа к отдельным элементам набора данных, обычно через методы `__len__` и `__getitem__` класса `torch.utils.data.Dataset`.

## Инженерное назначение

Dataset инкапсулирует получение и подготовку одного объекта обучения, гарантирует стабильный формат результата и отделяет источник данных от DataLoader, training loop и модели.

## Причина существования

Без отдельного контракта доступа чтение файлов, индексация и подготовка examples смешивались бы с моделью или обучением. Стабильный интерфейс позволяет менять источник данных без изменения остальных компонентов.

## Простое объяснение

Dataset описывает, как получить один объект обучения. В проекте `dataset.py` отвечает только за предоставление данных модели. Если выходной формат сохраняется, модель не должна знать, откуда пришли данные.

## Как это работает

1. `__len__` сообщает количество доступных объектов.
2. `__getitem__(index)` возвращает объект по индексу.
3. Dataset гарантирует формат, например `(features, label)`.
4. [[PyTorch/DataLoader|DataLoader]] получает элементы Dataset и собирает batches.
5. Источник данных можно заменить, сохранив тот же интерфейс.

## Пример

```python
from torch.utils.data import Dataset

class MyDataset(Dataset):
    def __len__(self):
        return 0

    def __getitem__(self, index):
        raise NotImplementedError
```

## Типичные ошибки

- Смешивать Dataset и DataLoader.
- Возвращать данные неправильного dtype, shape или формата.
- Выполнять обучение модели внутри Dataset.
- Встраивать чтение файлов непосредственно в модель.
- Считать Dataset местом хранения модели.

## Связанные темы

[[PyTorch/DataLoader|DataLoader]] · [[PyTorch/Tensor|Tensor]] · [[PyTorch/Tensors/Tensor Dtype|Tensor Dtype]] · [[PyTorch/Shape|Shape]] · [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]] · [[PyTorch/Интерфейс важнее реализации|Интерфейс важнее реализации]]

## Вопросы для проверки

- Что должен возвращать `__getitem__`?
- Чем Dataset отличается от DataLoader?
- Почему модель не должна знать источник данных?
- Какой контракт Dataset должен сохранять при замене реализации?

## Следующие темы

[[PyTorch/DataLoader|DataLoader]] · [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]]
