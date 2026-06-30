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
  - torch.bmm
  - Batch Matrix Multiplication
---

# Batch Matrix Multiplication

## Кратко

Для вычисления Scores между Q и K в Transformer используется batch matrix multiplication.

## Простое объяснение

`b` в `bmm` означает batch. Операция применяется сразу ко всем предложениям.

## Зачем это нужно

`torch.bmm()` позволяет эффективно вычислять Attention сразу для большого количества последовательностей.

## Как это работает

Обычное матричное умножение `torch.mm()` работает только с двумя матрицами. В Transformer одновременно обрабатывается целый batch предложений, поэтому используется `torch.bmm()`.

Если:

```text
Q   имеет размер (batch, seq, d)
K^T имеет размер (batch, d, seq)
```

то `torch.bmm()` возвращает:

```text
(batch, seq, seq)
```

## Пример

```python
attn_scores = torch.bmm(
    q,
    k.transpose(-2, -1),
)
```

## Типичные ошибки

- Считать `b` обозначением bias.
- Путать `bmm` с `mm`.

## Вопросы для проверки

- Чем `bmm` отличается от `mm`?
- Почему Transformer использует batch matrix multiplication?

## Следующие темы

- [[MultiheadAttention в PyTorch]]

## Связанные темы

- [[Attention Scores]] · [[Query Key Value]] · [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch]]
