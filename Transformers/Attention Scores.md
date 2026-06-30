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
difficulty: hard
aliases:
  - Dot Product Attention
  - Similarity Matrix
---

# Attention Scores

## Кратко

Attention начинается с вычисления матрицы похожести между Query и Key.

## Простое объяснение

Каждый токен сравнивается со всеми токенами предложения. Получается таблица внимания.

## Зачем это нужно

Scores определяют, на какие слова должен смотреть каждый токен.

## Как это работает

Формула:

```text
Scores = QK^T
```

Размерности:

```text
Q      (batch, seq, d)
K      (batch, seq, d)
K^T    (batch, d, seq)
Scores (batch, seq, seq)
```

Для предложения длиной `N` получается матрица внимания `N x N`.

## Пример

```python
scores = Q @ K.transpose(-2, -1)
```

## Типичные ошибки

- Считать Scores вероятностями.
- Считать Scores новым embedding.

## Вопросы для проверки

- Что означает размерность `(seq x seq)`?
- Что показывает каждая строка матрицы?

## Следующие темы

- [[Attention Weights]]

## Связанные темы

- [[Query Key Value]] · [[Attention Weights]] · [[Neural Networks/Softmax|Softmax]]
