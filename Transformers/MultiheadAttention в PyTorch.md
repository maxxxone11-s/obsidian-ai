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
  - in_proj_weight
  - packed projection
---

# MultiheadAttention в PyTorch

## Кратко

Учебная реализация Q, K и V может использовать три отдельных слоя, но PyTorch объединяет их в одну большую матрицу.

## Простое объяснение

Это оптимизация производительности. Алгоритм не меняется.

## Зачем это нужно

Современные библиотеки часто реализуют математически одинаковые операции значительно эффективнее.

## Как это работает

PyTorch хранит packed projection:

```text
(3 x embed_dim, embed_dim)
```

Например, если `embed_dim = 128`, то `in_proj_weight` имеет размер:

```text
(384, 128)
```

Затем результат одной большой проекции разбивается на три части.

```text
x
↓
Linear(128 -> 384)
↓
chunk()
↓
Q, K, V
```

## Пример

```python
q, k, v = _in_projection_packed(...)
```

## Типичные ошибки

- Считать packed projection новым алгоритмом.
- Путать оптимизацию реализации с изменением математики.

## Вопросы для проверки

- Почему используется одна большая матрица?
- Почему это быстрее?

## Следующие темы

- Multi Head Attention Source Code
- Transformer Block

## Связанные темы

- [[Query Key Value]] · [[PyTorch/nn.Linear|nn.Linear]] · [[Attention Scores]]
