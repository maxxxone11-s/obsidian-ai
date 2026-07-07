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
difficulty: hard
aliases:
  - in_proj_weight
  - packed projection
  - MultiheadAttention Implementation
---

# MultiheadAttention в PyTorch

## Академическое определение

`nn.MultiheadAttention` — PyTorch-реализация [[Multi-Head Attention]], где QKV projection, разделение на головы, batch matrix multiplication и output projection выполняются через оптимизированные tensor operations.

## Инженерное назначение

Эта реализация позволяет вычислять все attention heads эффективно и без Python-циклов по головам.

В инженерном коде PyTorch головы обычно представлены не отдельными объектами, а дополнительными измерениями Tensor и временными изменениями shape.

Поэтому чтение реализации требует отслеживать [[Attention Tensor Shapes]] на каждом шаге.

## Причина существования

Наивная реализация с отдельным объектом для каждой головы усложнила бы код и увеличила накладные расходы.

PyTorch использует packed projections, reshape/view/transpose и [[Batch Matrix Multiplication]], чтобы выполнить ту же математику быстрее.

## Простое объяснение

Алгоритм Multi-Head Attention не меняется. Меняется только способ эффективного выполнения.

PyTorch не создает отдельный Python-класс для каждой головы. Он пересобирает Tensor так, чтобы головы стали дополнительной размерностью или временно частью batch.

## Как это работает

Сначала PyTorch хранит packed projection:

```text
(3 x embed_dim, embed_dim)
```

Если `embed_dim = 128`, то `in_proj_weight` имеет размер:

```text
(384, 128)
```

После одной большой проекции результат разбивается на Q, K и V:

```text
x
↓
Linear(128 -> 384)
↓
chunk()
↓
Q, K, V
```

Затем для heads меняется форма Tensor:

```text
(batch, seq, embed_dim)
↓
(batch, seq, heads, head_dim)
↓
(batch, heads, seq, head_dim)
```

Для `torch.bmm()` batch и heads могут временно объединяться:

```text
(batch, heads, seq, head_dim)
↓
(batch × heads, seq, head_dim)
```

После вычислений исходная структура восстанавливается, результаты heads объединяются через Concat, затем применяется output projection.

`split heads`, `transpose`, `view` и `reshape` меняют форму Tensor для удобства вычислений, но не являются новыми attention-операциями сами по себе.

## Пример

```python
q, k, v = _in_projection_packed(...)
```

Формы:

```text
(32, 20, 512)
↓
(32, 20, 8, 64)
↓
(32, 8, 20, 64)
↓
(256, 20, 64)
```

## Типичные ошибки

- Считать packed projection новым алгоритмом.
- Путать оптимизацию реализации с изменением математики.
- Думать, что QKV исчезли.
- Ожидать отдельный Python-объект Head для каждой головы.
- Считать `view`, `reshape` и `transpose` вычислением Attention, а не изменением формы Tensor.
- Терять общий pipeline из-за отдельных операций изменения shape.
- Считать появление оси heads изменением смысла данных.

## Связанные темы

[[Multi-Head Attention]] · [[Attention Tensor Shapes]] · [[CausalSelfAttention.forward Pipeline]] · [[Query Key Value]] · [[PyTorch/nn.Linear|nn.Linear]] · [[Attention Scores]] · [[Batch Matrix Multiplication]] · [[Module и Functional в PyTorch]] · [[PyTorch/View|View]] · [[PyTorch/Reshape|Reshape]]

## Вопросы для проверки

- Почему используется одна большая матрица для QKV?
- Как из `in_proj_weight` получают Q, K и V?
- Почему головы представлены размерностью Tensor, а не отдельными объектами?
- Зачем временно объединять `batch` и `heads`?
- Что делает output projection после Concat?
- Какие операции меняют shape, но не вычисляют Attention?

## Следующие темы

- `multi_head_attention_forward()`
- Attention Mask
- Causal Mask
- Padding Mask
- PyTorch Source Code
