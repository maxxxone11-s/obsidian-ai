---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-06
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - nanoGPT Architecture
  - GPT.__init__
---

# nanoGPT Architecture

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

nanoGPT Architecture — минимальная реализация GPT, организующая модель как набор независимых компонентов: Token Embedding, Position Embedding, список Transformer Block и финальную LayerNorm.

Компоненты модели создаются на основе [[GPTConfig]], который задаёт размеры и ключевые гиперпараметры архитектуры.

## Инженерное назначение

nanoGPT показывает, как Transformer собирается из отдельных модулей в реальном коде.

Архитектура разделяет модель на логические части, которые проще читать, тестировать и сопоставлять с теорией.

Единый config помогает создать `wte`, `wpe`, `drop`, `h` и `ln_f` согласованно.

## Причина существования

Модульная структура делает архитектуру повторно используемой и понятной.

Без такого разделения сложно увидеть, где создаются embeddings, где выполняются blocks и где находится финальная нормализация.

Без единой конфигурации разные части модели могли бы ожидать разные размерности.

## Простое объяснение

GPT собирается как конструктор из отдельных компонентов.

Каждый block имеет одинаковую архитектуру, но собственные независимые параметры.

`GPTConfig` — это чертёж, по которому создаются эти компоненты.

## Как это работает

Основные элементы:

```text
wte  — Token Embedding
wpe  — Position Embedding
drop — Dropout после объединения embeddings
h    — список Transformer Block
ln_f — финальная LayerNorm
```

Каждый Block создается как отдельный объект. Архитектура блоков одинакова, но параметры каждого блока независимы.

Обычно `h` хранится в [[ModuleList]], чтобы PyTorch зарегистрировал все blocks как части модели.

Ключевые параметры config:

```text
block_size — максимальная длина контекста
vocab_size — размер словаря токенов
n_layer    — количество Transformer Block
n_head     — количество Attention Head
n_embd     — размер embedding
dropout    — вероятность Dropout
bias       — использовать ли bias в Linear и LayerNorm
```

## Пример

```text
config.n_layer = 12
↓
создаются 12 независимых Block
```

Каждый Block имеет собственные веса Attention, MLP и LayerNorm.

Перед первым block token embedding и position embedding складываются, а затем применяется [[Neural Networks/Dropout|Dropout]]:

```text
tok_emb + pos_emb
    ↓
drop
    ↓
Transformer Blocks
```

## Типичные ошибки

- Считать, что все Transformer Block используют общие веса.
- Путать одинаковую архитектуру с одинаковыми параметрами.
- Делать вывод по синтаксису Python без учета создания новых объектов при каждом вызове конструктора.
- Путать гиперпараметры в GPTConfig с обучаемыми весами.
- Считать Dropout частью таблицы WTE.
- Не понимать, зачем `h` хранится в ModuleList, а не в обычном Python list.

## Связанные темы

[[GPTConfig]] · [[Transformer Block]] · [[ModuleList]] · [[Embedding Layer]] · [[Position Embedding]] · [[LayerNorm]] · [[Feed Forward Network]] · [[Multi-Head Attention]] · [[Neural Networks/Dropout|Dropout]]

## Вопросы для проверки

- Что означает `wte`?
- Что означает `wpe`?
- Что означает `drop`?
- Что означает `h`?
- Какие параметры config определяют архитектуру модели?
- Почему каждый Block имеет собственные веса?

## Следующие темы

- Reading nanoGPT Forward Pass
- GPT.forward()
- [[ModuleList]]
