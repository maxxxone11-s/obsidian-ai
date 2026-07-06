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
  - Positional Embedding
  - WPE
  - Position Lookup Table
---

# Position Embedding

## Академическое определение

Position Embedding — отдельная обучаемая таблица embedding позиций, которая хранит информацию о порядке токенов независимо от [[Embedding Layer|Token Embedding]].

Каждая строка WPE соответствует позиции токена в последовательности.

## Инженерное назначение

Position Embedding позволяет разделить информацию о смысле токена и его положении в последовательности, не увеличивая размерность embedding.

В GPT-подобной архитектуре token embedding и position embedding складываются перед входом в первый [[Transformer Block]].

WTE отвечает за смысл токена, а WPE отвечает за его позицию.

## Причина существования

Если хранить embedding для каждой пары `(токен, позиция)`, количество параметров становится огромным.

Разделение на две таблицы позволяет повторно использовать один и тот же Token Embedding независимо от позиции.

Self-Attention сам по себе не знает порядок элементов последовательности, поэтому позиционную информацию нужно добавить явно.

## Простое объяснение

Один embedding отвечает за значение слова, второй — за его место в предложении.

Затем они складываются.

## Как это работает

Модель создает последовательность индексов позиций через `torch.arange()`, получает Position Embedding из WPE и складывает его с Token Embedding:

```python
x = tok_emb + pos_emb
```

Сложение используется вместо concat, чтобы сохранить постоянную размерность embedding во всей архитектуре Transformer.

```text
(20, 4096) + (20, 4096) -> (20, 4096)
```

Concat удвоил бы размерность embedding и потребовал бы изменить все последующие Linear-слои, Attention, MLP, Residual и LayerNorm.

Обе таблицы имеют одинаковую размерность `n_embd`, потому что сложение выполняется покоординатно.

## Пример

Слово `Transformer` имеет одинаковый Token Embedding независимо от того, находится оно на позиции 5 или 500. Меняется только Position Embedding.

## Типичные ошибки

- Считать, что Position Embedding хранит пары "слово + позиция".
- Считать, что WPE зависит от конкретных слов.
- Считать WPE частью WTE.
- Считать WPE вычислением позиции, а не lookup в обучаемой таблице.
- Считать, что складывание увеличивает размерность embedding.
- Считать, что concat и сложение эквивалентны.

## Связанные темы

[[Embedding Layer]] · [[Transformer Block]] · [[nanoGPT Architecture]] · [[GPTConfig]]

## Вопросы для проверки

- Почему Position Embedding хранится отдельно от Token Embedding?
- Чем WPE отличается от WTE?
- Почему обе таблицы имеют одинаковую размерность?
- Почему используется сложение, а не concat?
- Что происходит с размерностью после сложения?

## Следующие темы

- Transformer Input Pipeline
- [[nanoGPT Architecture]]
