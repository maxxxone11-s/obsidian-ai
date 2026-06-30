---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - inference
  - classification
confidence: 0.98
difficulty: easy
---

# top_k

## Простое объяснение

`top_k` позволяет получить несколько наиболее вероятных классов вместо одного ответа.

## Зачем это нужно

Используется в классификации изображений и LLM, когда полезно показать несколько лучших вариантов.

## Как это работает

```text
top_k = 1 -> лучший класс
top_k = 3 -> три лучших класса
```

`torch.topk()` возвращает значения вероятностей и индексы классов.

## Пример

```python
values, indices = torch.topk(probabilities, k=3)
```

## Типичные ошибки

- Путать значения вероятностей и индексы классов.

## Вопросы для проверки

- Что возвращает `topk()`?
- Чем отличаются `values` и `indices`?

## Следующие темы

- Beam Search

## Связанные темы

- [[Inference Pipeline]] · [[Neural Networks/Softmax|Softmax]] · [[predict()]]
