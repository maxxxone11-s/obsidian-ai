---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: medium
difficulty: hard
aliases:
  - Progressive Representation Learning
  - Iterative Context Refinement
---

# Постепенное уточнение embedding

## Кратко

Transformer не пытается сразу построить идеальное представление токена. Каждый Transformer Block немного изменяет embedding, и после каждого блока представление становится более информативным.

## Простое объяснение

Каждый Transformer Block делает небольшой шаг. Представление слова постепенно становится все более соответствующим текущему контексту.

## Зачем это нужно

Постепенное уточнение позволяет LLM учитывать длинный контекст и сложные зависимости между словами.

## Как это работает

Исходный embedding используется как основа. Каждый новый блок добавляет новую информацию, а полученный embedding становится входом следующего блока.

```text
Initial Embedding
    ↓
Attention
    ↓
Residual
    ↓
Feed Forward
    ↓
Новый Embedding
    ↓
Следующий Transformer Block
    ↓
Еще более информативный Embedding
```

## Пример

Token `bank` после каждого блока становится все более похожим на представление `bank(finance)` либо `bank(river)` в зависимости от окружающего контекста.

## Типичные ошибки

- Считать каждый Attention полностью независимым.
- Ожидать мгновенного формирования контекстного embedding после первого блока.

## Вопросы для проверки

- Почему требуется несколько Transformer Block?
- Что происходит после каждого блока?

## Следующие темы

- [[Transformer Block]]
- [[LayerNorm]]

## Связанные темы

- [[Embedding Space]] · [[Статический и контекстный Embedding]] · [[Residual Connection]]
