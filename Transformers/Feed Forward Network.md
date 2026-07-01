---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-01
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - FFN
  - FeedForward Network
  - Position-wise Feed Forward
  - Position-wise MLP
  - MLP
---

# Feed Forward Network

## Академическое определение

Feed Forward Network в Transformer — небольшая полносвязная нейронная сеть, которая применяется независимо к каждому embedding после Self-Attention.

Типичная структура:

```text
Linear
  ↓
GELU / ReLU
  ↓
Linear
```

## Инженерное назначение

FeedForward не занимается взаимодействием токенов. Его ответственность — построить новые признаки из уже собранной контекстной информации.

Внутри [[Transformer Block]] он идет после Attention-части и обрабатывает каждый токен отдельно.

## Причина существования

Self-Attention отвечает за обмен информацией между токенами, но после получения контекста требуется дополнительная нелинейная обработка embedding.

Именно эту задачу решает FeedForward Network: он извлекает новые признаки из уже собранной информации.

## Простое объяснение

Attention отвечает на вопрос:

```text
Откуда взять информацию?
```

FeedForward отвечает:

```text
Какие новые признаки можно построить из уже полученной информации?
```

## Как это работает

Каждый embedding отдельно проходит через небольшую MLP. Другие токены на этом этапе уже не участвуют в вычислениях.

Обычно размерность сначала увеличивается, а затем возвращается обратно:

```text
768 → 3072 → 768
```

Это позволяет сети строить более сложные признаки.

## Пример

```python
nn.Sequential(
    nn.Linear(d_model, hidden),
    nn.GELU(),
    nn.Linear(hidden, d_model),
)
```

## Типичные ошибки

- Путать FeedForward с методом `forward()`.
- Считать FeedForward всей моделью Transformer.
- Считать FeedForward частью Self-Attention.
- Считать FeedForward механизмом общения между токенами.
- Недостаточно различать архитектурную роль Attention и FeedForward.

## Связанные темы

[[Transformer Block]] · [[LayerNorm]] · [[Residual Connection]] · [[PyTorch/nn.Linear|nn.Linear]] · [[Neural Networks/ReLU|ReLU]]

## Вопросы для проверки

- Почему FeedForward является обычной MLP?
- Чем FeedForward отличается от Self-Attention?
- Какие задачи решает FeedForward?
- Почему токены не взаимодействуют внутри FeedForward?

## Следующие темы

- Multi-Head Attention
- Transformer Block Optimization
- [[MultiheadAttention в PyTorch]]
