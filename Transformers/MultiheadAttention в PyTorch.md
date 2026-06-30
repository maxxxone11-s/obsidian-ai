---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: high
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

Современные библиотеки часто реализуют математически одинаковые операции значительно эффективнее. Одно большое матричное умножение обычно быстрее трех отдельных операций.

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

Учебная реализация Self-Attention использует три независимых Linear слоя. В реализации PyTorch Q, K и V не исчезают: они получаются после одной большой операции и последующего `chunk`.

## Пример

```python
q, k, v = _in_projection_packed(...)
```

## Типичные ошибки

- Считать packed projection новым алгоритмом.
- Путать оптимизацию реализации с изменением математики.
- Думать, что QKV исчезли.

## Вопросы для проверки

- Почему используется одна большая матрица?
- Почему это быстрее?
- Как из `in_proj_weight` получают Q, K и V?

## Следующие темы

- Multi Head Attention Source Code
- [[Transformer Block]]
- [[Batch Matrix Multiplication]]

## Связанные темы

- [[Query Key Value]] · [[PyTorch/nn.Linear|nn.Linear]] · [[Attention Scores]] · [[Module и Functional в PyTorch]]
