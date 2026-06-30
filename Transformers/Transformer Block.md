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
difficulty: medium
aliases:
  - Transformer Layer
  - Encoder Block
  - Decoder Block
---

# Transformer Block

## Кратко

Transformer состоит не из одного механизма Self-Attention, а из повторяющихся Transformer Block. Каждый блок последовательно обрабатывает входные embedding и постепенно уточняет их представление.

## Простое объяснение

Один Transformer Block - это один этап "размышления" модели. Каждый следующий блок получает уже более информативные embedding и делает их еще точнее.

## Зачем это нужно

Практически все современные LLM построены как последовательность Transformer Block. GPT, Llama, Claude и Gemini отличаются деталями реализации, но общий принцип остается похожим.

## Как это работает

Классический Transformer Block содержит основные стадии:

1. Multi-Head Self-Attention.
2. Residual Connection.
3. Layer Normalization.
4. Feed Forward Network.

После Feed Forward снова используются Residual Connection и Layer Normalization.

```text
x
│
▼
Multi-Head Attention
│
▼
Residual (+)
│
▼
LayerNorm
│
▼
Feed Forward
│
▼
Residual (+)
│
▼
LayerNorm
│
▼
Output
```

Полученный embedding становится входом следующего Transformer Block.

## Пример

GPT-2 использует 12 Transformer Block. GPT-3 использует десятки Transformer Block. Современные большие модели могут использовать более 80-100 подобных блоков.

## Типичные ошибки

- Считать Self-Attention всей архитектурой Transformer.
- Считать Transformer одним большим слоем.
- Думать, что после Attention сразу получается ответ модели.

## Вопросы для проверки

- Какие основные компоненты входят в Transformer Block?
- Почему Transformer состоит из множества одинаковых блоков?
- Что происходит между двумя соседними Attention?

## Следующие темы

- [[Residual Connection]]
- [[LayerNorm]]
- [[Feed Forward Network]]

## Связанные темы

- [[MultiheadAttention в PyTorch]] · [[Residual Connection]] · [[LayerNorm]] · [[Feed Forward Network]]
