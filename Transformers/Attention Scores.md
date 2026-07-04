---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-04
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Dot Product Attention
  - Similarity Matrix
  - Scaled Dot-Product Attention
  - Attention Scaling
---

# Attention Scores

## Академическое определение

Attention Scores — матрица похожести между Query и Key, которая показывает, насколько каждый токен должен обратить внимание на каждый другой токен.

В Transformer scores обычно вычисляются как scaled dot-product:

```text
Scores = QK^T / sqrt(head_dim)
```

## Инженерное назначение

Scores являются промежуточным сигналом релевантности до применения [[Neural Networks/Softmax|Softmax]].

Масштабирование через `sqrt(head_dim)` удерживает значения scores в стабильном диапазоне, чтобы Softmax не становился слишком резким и обучение не теряло полезные градиенты.

## Причина существования

Attention должен решить, какие токены релевантны друг другу.

При увеличении размерности головы скалярные произведения становятся значительно больше. Без масштабирования Softmax почти всегда выбирал бы один токен с вероятностью, близкой к единице.

## Простое объяснение

Каждый токен сравнивается со всеми токенами предложения.

Получается таблица внимания, но это ещё не вероятности. Перед Softmax значения уменьшают делением на `sqrt(head_dim)`, чтобы распределение внимания оставалось обучаемым.

## Как это работает

```text
Q      (batch, heads, seq, head_dim)
K      (batch, heads, seq, head_dim)
K^T    (batch, heads, head_dim, seq)
Scores (batch, heads, seq, seq)
```

Формула:

```text
scores = Q @ K.transpose(-2, -1)
scores = scores / sqrt(head_dim)
```

После этого могут применяться [[Causal Mask]] и Softmax.

## Пример

```python
scores = Q @ K.transpose(-2, -1)
scores = scores / (head_dim ** 0.5)
```

Вместо слишком больших scores:

```text
[120, 80, 20]
```

модель использует уменьшенные значения, что позволяет Softmax сохранить информативное распределение внимания.

## Типичные ошибки

- Считать Scores вероятностями.
- Считать Scores новым embedding.
- Считать масштабирование случайной константой.
- Считать, что масштабирование нужно только для численной стабильности.
- Не связывать большие scores с поведением Softmax.

## Связанные темы

[[Query Key Value]] · [[Attention Weights]] · [[Causal Mask]] · [[Self-Attention Pipeline]] · [[Neural Networks/Softmax|Softmax]] · [[Statistics/Standard Deviation|Standard Deviation]]

## Вопросы для проверки

- Что означает размерность `(seq x seq)`?
- Что показывает каждая строка матрицы?
- Почему большие Scores вредят обучению?
- Почему используется именно `sqrt(head_dim)`?

## Следующие темы

- [[Attention Weights]]
- [[Causal Mask]]
- Training Stability
