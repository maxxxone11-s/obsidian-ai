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
  - QKV
  - Query Key Value
---

# Query Key Value

## Кратко

После получения embedding создаются три разных представления каждого токена: Query, Key и Value. Они вычисляются отдельными линейными слоями.

## Простое объяснение

Один embedding используется три раза, но каждый раз применяется своя матрица весов. Поэтому получаются разные представления.

## Зачем это нужно

Transformer разделяет роли:

- Query - что искать.
- Key - по каким признакам меня можно найти.
- Value - какую информацию я передаю.

## Как это работает

Формулы:

```text
Q = XWq
K = XWk
V = XWv
```

где `X` - embedding, а `Wq`, `Wk`, `Wv` - разные обучаемые матрицы.

```text
x → Linear(Wq) → Query
x → Linear(Wk) → Key
x → Linear(Wv) → Value
```

## Пример

```python
self.query = nn.Linear(d_model, d_model)
self.key = nn.Linear(d_model, d_model)
self.value = nn.Linear(d_model, d_model)
```

## Типичные ошибки

- Считать, что Q, K и V одинаковые.
- Считать, что используется одна матрица весов.

## Вопросы для проверки

- Почему используются три разных матрицы?
- Что произойдет, если использовать одну матрицу?

## Следующие темы

- [[Attention Scores]]
- [[MultiheadAttention в PyTorch]]

## Связанные темы

- [[Embedding Layer]] · [[Attention Scores]] · [[PyTorch/nn.Linear|nn.Linear]]
