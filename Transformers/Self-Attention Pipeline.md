---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-07
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Attention Pipeline
  - Self-Attention Forward Pass
---

# Self-Attention Pipeline

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

Self-Attention Pipeline — последовательность инженерных операций, которая преобразует embedding в новый контекстный embedding через QKV, scaled scores, optional mask, weights и weighted sum по Value.

## Инженерное назначение

Pipeline позволяет каждому токену получить информацию от наиболее важных токенов последовательности.

Он связывает отдельные concepts Attention в единую вычислительную цепочку.

В decoder-only Transformer этот pipeline также включает [[Causal Mask]], чтобы сохранить autoregressive-ограничение.

В nanoGPT-подобном коде та же цепочка реализуется внутри [[CausalSelfAttention.forward Pipeline]].

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
c_attn
  ↓
Q, K, V
  ↓
Split heads
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
Concat heads
  ↓
c_proj
  ↓
Новый embedding
```

Value впервые используется только на этапе получения нового embedding:

```text
output = softmax(mask(QK^T / sqrt(head_dim))) @ V
```

После weighted sum по Value результаты heads объединяются и проходят через `c_proj`, а затем через residual dropout.

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
- Путать `c_attn`, который создает QKV, и `c_proj`, который смешивает результаты heads.
- Смешивать уровни `GPT.forward`, `Block.forward` и `CausalSelfAttention.forward`.

## Связанные темы

[[CausalSelfAttention.forward Pipeline]] · [[Attention Tensor Shapes]] · [[Query Key Value]] · [[Attention Scores]] · [[Causal Mask]] · [[Attention Weights]] · [[Attention Output]] · [[Multi-Head Attention]]

## Вопросы для проверки

- На каком этапе впервые используется Value?
- Чем отличаются Attention Scores и Attention Weights?
- Почему новый embedding получается только после умножения на V?
- Где в pipeline применяются scaling и causal mask?
- Где в pipeline находится output projection?
- Почему вход и выход Self-Attention имеют одинаковую внешнюю shape?

## Следующие темы

- [[Multi-Head Attention]]
- [[Causal Mask]]
- [[CausalSelfAttention.forward Pipeline]]
- Output Projection
