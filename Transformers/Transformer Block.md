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
  - Transformer Layer
  - Encoder Block
  - Decoder Block
---

# Transformer Block

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

Transformer Block — повторяющийся модуль Transformer-архитектуры, который последовательно обрабатывает входные embedding и постепенно уточняет их представление.

Каждый block имеет одинаковую архитектуру, но собственный независимый набор параметров.

## Инженерное назначение

Transformer Block является основной вычислительной единицей LLM.

В GPT-подобной модели последовательность blocks позволяет постепенно строить всё более сложные представления токенов. Разные block-и могут изучать разные уровни признаков, потому что не делят одни и те же веса.

## Причина существования

Один Self-Attention не является всей архитектурой Transformer.

Модель нуждается в повторяющихся этапах обработки: attention собирает контекст, residual сохраняет старое представление, normalization стабилизирует масштаб, а feed forward строит новые признаки.

Внутри block Attention и FeedForward решают принципиально разные задачи: Attention обменивается информацией между токенами, а FeedForward преобразует признаки внутри каждого токена независимо.

Если бы все blocks использовали общие веса, способность модели постепенно усложнять представление признаков была бы ограничена.

## Простое объяснение

Один Transformer Block — это один этап обработки embedding.

Код block-ов может быть одинаковым, но веса внутри каждого экземпляра разные.

Attention отвечает на вопрос: "у каких токенов взять информацию?". FeedForward отвечает: "что нового вычислить внутри этого embedding?".

## Как это работает

Классический Transformer Block содержит основные стадии:

1. Multi-Head Self-Attention.
2. Residual Connection.
3. Layer Normalization.
4. Feed Forward Network.

После Feed Forward снова используются Residual Connection и Layer Normalization.

Attention использует информацию соседних токенов. FeedForward работает только с embedding текущего токена.

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

В nanoGPT-подобной реализации каждый вызов `Block(config)` создает новый объект со случайно инициализированными параметрами.

```text
Block1: Wq1, Wk1, Wv1
Block2: Wq2, Wk2, Wv2
```

Это разные матрицы весов.

## Пример

GPT-2 использует 12 Transformer Block. GPT-3 использует десятки Transformer Block. Современные большие модели могут использовать более 80-100 подобных блоков.

Если `config.n_layer = 12`, модель создает 12 независимых экземпляров `Block(config)`.

## Типичные ошибки

- Считать Self-Attention всей архитектурой Transformer.
- Считать Transformer одним большим слоем.
- Думать, что после Attention сразу получается ответ модели.
- Считать все Block одним объектом.
- Путать одинаковую архитектуру с одинаковыми параметрами.
- Думать, что повторное использование класса означает повторное использование весов.
- Считать MLP продолжением Attention.
- Считать FeedForward модулем взаимодействия между токенами.

## Связанные темы

[[MultiheadAttention в PyTorch]] · [[Multi-Head Attention]] · [[Residual Connection]] · [[LayerNorm]] · [[Feed Forward Network]] · [[ModuleList]] · [[Постепенное уточнение embedding]] · [[GPTConfig]]

## Вопросы для проверки

- Какие основные компоненты входят в Transformer Block?
- Почему Transformer состоит из множества одинаковых блоков?
- Что происходит между двумя соседними Attention?
- Почему каждый Block имеет собственные веса?
- Что произошло бы при использовании одного объекта Block несколько раз?
- Какие задачи решает Attention?
- Какие задачи решает FeedForward?

## Следующие темы

- [[Residual Connection]]
- [[LayerNorm]]
- [[Feed Forward Network]]
- [[ModuleList]]
