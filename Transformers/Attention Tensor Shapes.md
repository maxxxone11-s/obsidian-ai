---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-07
updated: 2026-07-07
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Attention Tensor Shapes
  - Tensor Flow in Attention
---

# Attention Tensor Shapes

## Академическое определение

Attention Tensor Shapes — последовательность форм Tensor внутри Self-Attention, где на каждом этапе Tensor изменяет форму в соответствии с выполняемой операцией, сохраняя согласованность размерностей.

## Инженерное назначение

Понимание shapes позволяет читать и отлаживать реализацию Multi-Head Attention без потери смысла данных.

Это особенно важно для операций `split`, `view`, `reshape`, `transpose`, `matmul` и concat heads.

## Причина существования

Каждая операция attention требует определенной структуры Tensor.

QKV-проекция требует объединённой размерности `3C`, heads требуют отдельной оси `H`, а scores требуют матрицу связей `(T, T)`.

## Простое объяснение

Tensor постоянно меняет форму, но не смысл данных.

Форма меняется для удобства вычислений.

## Как это работает

Типовой путь shape:

```text
(B, T, C)
    ↓
(B, T, 3C)
    ↓
Q, K, V: три Tensor (B, T, C)
    ↓
(B, H, T, head_dim)
    ↓
(B, H, T, T)
    ↓
(B, H, T, head_dim)
    ↓
(B, T, C)
```

Где:

- `(B, T, C)` — batch, sequence length, embedding size.
- `H` — количество heads.
- `head_dim` — размерность одной head.

## Пример

```text
(4, 128, 768)
    ↓
(4, 128, 2304)
    ↓
Q, K, V
    ↓
(4, 12, 128, 64)
    ↓
(4, 12, 128, 128)
    ↓
(4, 128, 768)
```

## Типичные ошибки

- Терять понимание формы Tensor между операциями.
- Считать reshape изменением данных.
- Считать `transpose` вычислением Attention, а не подготовкой формы.
- Не понимать, где появляется размерность `n_head`.

## Связанные темы

[[CausalSelfAttention.forward Pipeline]] · [[MultiheadAttention в PyTorch]] · [[Batch Matrix Multiplication]] · [[Query Key Value]] · [[Attention Scores]] · [[PyTorch/View|View]] · [[PyTorch/Reshape|Reshape]]

## Вопросы для проверки

- Как меняется shape после `c_attn`?
- Когда появляется размерность `n_head`?
- Почему Attention Scores имеют форму `(B, H, T, T)`?
- Почему reshape не меняет смысл данных?

## Следующие темы

- Flash Attention
- [[Batch Matrix Multiplication]]
- [[MultiheadAttention в PyTorch]]
