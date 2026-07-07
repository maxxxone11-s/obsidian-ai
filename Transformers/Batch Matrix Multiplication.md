---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-07
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - torch.bmm
  - Batch Matrix Multiplication
  - Flatten Batch and Heads
  - bmm Optimization
---

# Batch Matrix Multiplication

## Академическое определение

Batch Matrix Multiplication — пакетное матричное умножение, при котором для каждого элемента batch выполняется отдельное матричное умножение.

В PyTorch для этого используется `torch.bmm()` с трехмерными тензорами.

## Инженерное назначение

`torch.bmm()` позволяет эффективно вычислять attention scores сразу для большого количества последовательностей или heads без Python-циклов.

В реализации [[MultiheadAttention в PyTorch]] batch и heads могут временно объединяться, чтобы каждая голова стала независимым элементом batch.

## Причина существования

Обычное `torch.mm()` работает только с двумя матрицами. В Transformer нужно одновременно обработать batch последовательностей и несколько attention heads.

Объединение batch и heads позволяет использовать оптимизированное пакетное матричное умножение вместо циклов по головам.

## Простое объяснение

`b` в `bmm` означает batch.

Для библиотеки каждая голова может временно стать отдельным элементом batch. После вычислений исходная структура восстанавливается.

## Как это работает

Если:

```text
Q   имеет размер (batch, seq, d)
K^T имеет размер (batch, d, seq)
```

то `torch.bmm()` возвращает:

```text
(batch, seq, seq)
```

В Multi-Head Attention форма может временно меняться так:

```text
(batch, heads, seq, head_dim)
↓
(batch × heads, seq, head_dim)
↓
torch.bmm()
↓
восстановление heads
```

Например:

```text
(32, 8, 20, 64)
↓
(256, 20, 64)
```

Для raw attention scores в multi-head форме:

```text
q:   (B, H, T, head_dim)
k^T: (B, H, head_dim, T)
↓
q @ k^T
↓
(B, H, T, T)
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
- Считать объединение batch и heads частью математического алгоритма.
- Считать изменение формы изменением данных.
- Ожидать цикл по головам в реализации PyTorch.
- Терять связь между `bmm` и формой Attention Scores `(T, T)`.

## Связанные темы

[[Multi-Head Attention]] · [[MultiheadAttention в PyTorch]] · [[Attention Tensor Shapes]] · [[Attention Scores]] · [[Query Key Value]] · [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch]]

## Вопросы для проверки

- Чем `bmm` отличается от `mm`?
- Почему Transformer использует batch matrix multiplication?
- Почему batch и heads временно объединяются?
- Что происходит после завершения вычислений?
- Почему результат `q @ k^T` имеет форму `(B, H, T, T)`?

## Следующие темы

- [[MultiheadAttention в PyTorch]]
- Attention Mask
- PyTorch Source Code
