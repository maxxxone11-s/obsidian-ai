---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-03
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - nanoGPT Architecture
---

# nanoGPT Architecture

## Академическое определение

nanoGPT Architecture — минимальная реализация GPT, организующая модель как набор независимых компонентов: Token Embedding, Position Embedding, список Transformer Block и финальную LayerNorm.

## Инженерное назначение

nanoGPT показывает, как Transformer собирается из отдельных модулей в реальном коде.

Архитектура разделяет модель на логические части, которые проще читать, тестировать и сопоставлять с теорией.

## Причина существования

Модульная структура делает архитектуру повторно используемой и понятной.

Без такого разделения сложно увидеть, где создаются embeddings, где выполняются blocks и где находится финальная нормализация.

## Простое объяснение

GPT собирается как конструктор из отдельных компонентов.

Каждый block имеет одинаковую архитектуру, но собственные независимые параметры.

## Как это работает

Основные элементы:

```text
wte  — Token Embedding
wpe  — Position Embedding
h    — список Transformer Block
ln_f — финальная LayerNorm
```

Каждый Block создается как отдельный объект. Архитектура блоков одинакова, но параметры каждого блока независимы.

## Пример

```text
config.n_layer = 12
↓
создаются 12 независимых Block
```

Каждый Block имеет собственные веса Attention, MLP и LayerNorm.

## Типичные ошибки

- Считать, что все Transformer Block используют общие веса.
- Путать одинаковую архитектуру с одинаковыми параметрами.
- Делать вывод по синтаксису Python без учета создания новых объектов при каждом вызове конструктора.

## Связанные темы

[[Transformer Block]] · [[Embedding Layer]] · [[LayerNorm]] · [[Feed Forward Network]] · [[Multi-Head Attention]]

## Вопросы для проверки

- Что означает `wte`?
- Что означает `wpe`?
- Почему каждый Block имеет собственные веса?

## Следующие темы

- Reading nanoGPT Forward Pass
- GPT.forward()
