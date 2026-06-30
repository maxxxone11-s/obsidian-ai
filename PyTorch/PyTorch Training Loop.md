---
type: concept
area: PyTorch
status: learned
created: 2026-06-28
updated: 2026-06-30
tags:
  - pytorch
  - training-loop
  - autograd
  - optimizer
confidence: 0.99
difficulty: medium
---

# PyTorch Training Loop

## Кратко

Полностью разобран цикл обучения модели.

## Простое объяснение

Каждый батч проходит одинаковые пять этапов.

## Зачем это нужно

Training Loop — главный цикл обучения любой модели PyTorch. В реальном проекте он обычно находится в [[train.py как центр обучения|train.py]].

## Как это работает

Базовый порядок:

```python
prediction = model(x)
loss = criterion(prediction, y)
optimizer.zero_grad()
loss.backward()
optimizer.step()
```

Каждая строка цикла соответствует одному действию:

- предсказание;
- вычисление ошибки;
- очистка старых градиентов;
- вычисление новых градиентов;
- обновление параметров.

Training Loop автоматизирует процесс, который раньше был выполнен вручную через [[Gradient Descent]].
В проектной структуре он соединяет [[Dataset]], [[DataLoader]], [[nn.Module|Model]], [[Machine Learning/Loss Function|Loss]] и [[torch.optim|Optimizer]].

## Пример

```python
for x, y in dataloader:
    prediction = model(x)
    loss = criterion(prediction, y)

    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
```

## Типичные ошибки

- Перепутать порядок `backward()` и `step()`.
- Считать, что градиенты появляются после `optimizer.step()`.
- Думать, что без `step()` не вычисляются градиенты. На самом деле они вычисляются, но веса не обновляются.
- Помещать архитектуру модели внутрь `train.py`.
- Считать `train.py` местом хранения модели.

## Вопросы для проверки

- Что делает `model(x)`?
- Что делает `criterion()`?
- Зачем нужен `zero_grad()`?
- Что делает `backward()`?
- Что делает `step()`?
- Почему порядок строк важен?
- Какие компоненты объединяет `train.py`?

## Следующие темы

- [[Dataset]]
- [[DataLoader]]
- [[train.py как центр обучения]]

## Связанные темы

- [[Autograd]]
- [[torch.optim]]
- [[model.parameters()]]
- [[CrossEntropyLoss]]
- [[loss.item()]]
- [[Weighted Average Loss]]
- [[Machine Learning/Gradient Descent|Gradient Descent]]
- [[Machine Learning/Loss Function|Loss Function]]
- [[nn.Linear]]
- [[train.py как центр обучения]]
