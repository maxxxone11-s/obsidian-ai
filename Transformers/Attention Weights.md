---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: medium
difficulty: medium
aliases:
  - Attention Weights
  - Softmax как нормализация Attention Scores
---

# Attention Weights

## Кратко

После вычисления Scores применяется Softmax. Он превращает произвольные значения в веса внимания.

## Простое объяснение

Теперь модель знает, какую долю информации брать от каждого слова.

## Зачем это нужно

Scores нельзя использовать напрямую. Нужны нормализованные коэффициенты.

## Как это работает

Формула:

```text
Attention = softmax(Scores)
```

Свойства:

- все веса положительны;
- сумма весов каждой строки равна 1.

Например:

```text
[2.1, 1.7, 5.9] → [0.05, 0.12, 0.83]
```

## Пример

```python
weights = torch.softmax(scores, dim=-1)
```

## Типичные ошибки

- Считать Softmax вероятностью слова.
- Считать веса итоговым embedding.

## Вопросы для проверки

- Почему сумма весов равна 1?
- Что означает вес `0.83`?

## Следующие темы

- [[Attention Output]]

## Связанные темы

- [[Attention Scores]] · [[Attention Output]] · [[Neural Networks/Softmax|Softmax]]
