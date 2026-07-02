---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-02
tags:
  - transformers
confidence: medium
difficulty: hard
aliases:
  - QKV
  - Query Key Value
---

# Query Key Value

## Академическое определение

Query, Key и Value — три разные линейные проекции одного embedding, используемые attention-механизмом для вычисления связей между токенами и передачи информации.

Формулы:

```text
Q = XWq
K = XWk
V = XWv
```

## Инженерное назначение

QKV разделяют роли внутри Attention:

- Query описывает, что текущий токен ищет.
- Key описывает, по каким признакам токен можно найти.
- Value содержит информацию, которую токен передает.

В [[Multi-Head Attention]] каждая голова имеет собственные `Wq`, `Wk` и `Wv`.

## Причина существования

Если использовать один и тот же embedding без разных проекций, Attention не сможет разделить роли поиска, сопоставления и передачи информации.

Разные обучаемые матрицы позволяют одной и той же входной информации играть разные роли.

## Простое объяснение

Один embedding используется три раза, но каждый раз применяется своя матрица весов. Поэтому получаются разные представления.

В Multi-Head Attention все головы видят полный embedding, но каждая голова строит свою линейную проекцию.

## Как это работает

```text
x → Linear(Wq) → Query
x → Linear(Wk) → Key
x → Linear(Wv) → Value
```

Для head projection голова не получает фиксированный кусок embedding. Она получает результат обучаемой проекции:

```text
d_model → head_dim
```

Например:

```text
512 → 64
```

## Пример

```python
self.query = nn.Linear(d_model, d_model)
self.key = nn.Linear(d_model, d_model)
self.value = nn.Linear(d_model, d_model)
```

Для одной головы:

```text
Head1: X → Linear(512 -> 64)
Head2: X → Linear(512 -> 64)
```

Используются разные веса.

## Типичные ошибки

- Считать, что Q, K и V одинаковые.
- Считать, что используется одна матрица весов.
- Считать, что первая голова получает первые 64 признака embedding.
- Воспринимать разделение на головы как обычное разбиение массива.

## Связанные темы

[[Embedding Layer]] · [[Attention Scores]] · [[Multi-Head Attention]] · [[MultiheadAttention в PyTorch]] · [[PyTorch/nn.Linear|nn.Linear]]

## Вопросы для проверки

- Почему используются три разных матрицы?
- Что произойдет, если использовать одну матрицу?
- Почему головы используют линейную проекцию вместо разделения embedding?
- Какую проблему решает head projection?

## Следующие темы

- [[Attention Scores]]
- [[Multi-Head Attention]]
- [[MultiheadAttention в PyTorch]]
