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
difficulty: medium
aliases:
  - FFN
  - FeedForward Network
  - Position-wise Feed Forward
  - Position-wise MLP
  - MLP
  - MLP Expansion
  - c_fc
---

# Feed Forward Network

Область: [[Transformers/Transformers|Transformers]]

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

Первый Linear-слой FeedForward временно увеличивает размерность embedding для построения более сложных внутренних признаков.

## Причина существования

Self-Attention отвечает за обмен информацией между токенами, но после получения контекста требуется дополнительная нелинейная обработка embedding.

Именно эту задачу решает FeedForward Network: он извлекает новые признаки из уже собранной информации.

Более широкое внутреннее пространство позволяет модели сформировать больше комбинаций признаков перед возвращением к исходной размерности.

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
n_embd → 4 × n_embd → GELU → n_embd
```

Это позволяет сети строить более сложные признаки.

Attention использует информацию соседних токенов, а MLP работает только с embedding текущего токена.

## Пример

```python
nn.Sequential(
    nn.Linear(n_embd, 4 * n_embd),
    nn.GELU(),
    nn.Linear(4 * n_embd, n_embd),
)
```

Для `n_embd = 768`:

```text
768 → 3072 → GELU → 768
```

## Типичные ошибки

- Путать FeedForward с методом `forward()`.
- Считать FeedForward всей моделью Transformer.
- Считать FeedForward частью Self-Attention.
- Считать FeedForward механизмом общения между токенами.
- Недостаточно различать архитектурную роль Attention и FeedForward.
- Путать увеличение размерности MLP с QKV Projection.
- Считать коэффициент `4` обязательным математическим требованием.

## Связанные темы

[[Transformer Block]] · [[Multi-Head Attention]] · [[LayerNorm]] · [[Residual Connection]] · [[PyTorch/nn.Linear|nn.Linear]] · [[Neural Networks/ReLU|ReLU]]

## Вопросы для проверки

- Почему FeedForward является обычной MLP?
- Чем FeedForward отличается от Self-Attention?
- Какие задачи решает FeedForward?
- Почему токены не взаимодействуют внутри FeedForward?
- Почему FeedForward расширяет embedding?
- Чем расширение MLP отличается от QKV Projection?

## Следующие темы

- Multi-Head Attention
- SwiGLU
- GEGLU
- Transformer Block Optimization
- [[MultiheadAttention в PyTorch]]
