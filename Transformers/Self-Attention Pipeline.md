---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-04
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Attention Pipeline
---

# Self-Attention Pipeline

## Академическое определение

Self-Attention Pipeline — последовательность инженерных операций, которая преобразует embedding в новый контекстный embedding через QKV, scaled scores, optional mask, weights и weighted sum по Value.

## Инженерное назначение

Pipeline позволяет каждому токену получить информацию от наиболее важных токенов последовательности.

Он связывает отдельные concepts Attention в единую вычислительную цепочку.

В decoder-only Transformer этот pipeline также включает [[Causal Mask]], чтобы сохранить autoregressive-ограничение.

## Причина существования

Простое вычисление Q, K и V не изменяет embedding.

Чтобы получить новый контекстный embedding, нужно вычислить веса внимания и смешать информацию от других токенов через Value.

Без scaling scores могут стать слишком большими для стабильного Softmax, а без causal mask decoder во время обучения видел бы будущие токены.

## Простое объяснение

Сначала модель определяет важность остальных токенов, затем собирает их информацию согласно найденным весам.

## Как это работает

```text
Embedding
  ↓
Linear
  ↓
Q, K, V
  ↓
QK^T
  ↓
Attention Scores
  ↓
Scale by sqrt(head_dim)
  ↓
Causal Mask
  ↓
Softmax
  ↓
Attention Weights
  ↓
Attention Weights @ V
  ↓
Новый embedding
```

Value впервые используется только на этапе получения нового embedding:

```text
output = softmax(mask(QK^T / sqrt(head_dim))) @ V
```

## Пример

```python
scores = Q @ K.transpose(-2, -1)
scores = scores / (head_dim ** 0.5)
scores = scores.masked_fill(causal_mask == 0, float("-inf"))
weights = torch.softmax(scores, dim=-1)
output = weights @ V
```

## Типичные ошибки

- Считать, что `QK^T` уже является Attention.
- Считать, что Value участвует в вычислении Scores.
- Путать Scores и Attention Weights.
- Не понимать, что новый embedding получается только после умножения на V.
- Пропускать scaling и causal mask как "детали реализации", хотя они меняют поведение attention.

## Связанные темы

[[Query Key Value]] · [[Attention Scores]] · [[Causal Mask]] · [[Attention Weights]] · [[Attention Output]] · [[Multi-Head Attention]]

## Вопросы для проверки

- На каком этапе впервые используется Value?
- Чем отличаются Attention Scores и Attention Weights?
- Почему новый embedding получается только после умножения на V?
- Где в pipeline применяются scaling и causal mask?

## Следующие темы

- [[Multi-Head Attention]]
- [[Causal Mask]]
- Output Projection
