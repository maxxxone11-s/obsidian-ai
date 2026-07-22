---
type: concept
area: RAG
status: learned
created: 2026-07-12
updated: 2026-07-12
tags: [rag, context, generation, context-construction]
aliases: [Context Builder, Context Assembly]
confidence: high
difficulty: intermediate
---

# Context Construction

Область: [[RAG/RAG|RAG]]

## Академическое определение

Context Construction — этап Query Pipeline, который выбирает, дедуплицирует, объединяет, упорядочивает и ограничивает найденные chunks перед их включением в prompt.

## Инженерное назначение

Context Builder формирует наиболее полезный Final Context для LLM: уменьшает шум, удаляет повторы, объединяет соседние fragments и укладывает результат в доступный token budget.

## Причина существования

Retriever и reranker могут вернуть больше chunks, чем следует передавать модели. Сырые результаты могут повторяться, быть фрагментарными или превышать Context Window.

## Простое объяснение

Context Builder решает, какие найденные fragments действительно попадут в prompt и в каком порядке.

## Как это работает

1. Получает список [[RAG/SearchResult|SearchResult]] после retrieval и reranking.
2. Удаляет дубликаты.
3. При необходимости объединяет соседние chunks одного источника.
4. Отбрасывает лишние или слабые результаты.
5. Упорядочивает контекст и применяет token limit.
6. Передаёт Final Context в [[RAG/Prompt Construction|Prompt Construction]].

## Пример

Chunks 41, 42 и 43 из одного раздела объединяются в логический блок, а повторяющиеся fragments удаляются до формирования prompt.

## Типичные ошибки

- Путать Context Builder с [[RAG/Retrieval|Retriever]].
- Передавать модели все найденные документы без фильтрации.
- Объединять несвязанные chunks.
- Игнорировать token budget и порядок fragments.

## Связанные темы

[[RAG/Prompt Construction|Prompt Construction]] · [[RAG/Reranking|Reranker]] · [[RAG/SearchResult|SearchResult]] · [[RAG/Chunk|Chunk]] · [[LLM Engineering/Context Window|Context Window]] · [[RAG/Context Precision|Context Precision]] · [[RAG/Context Recall|Context Recall]]

## Вопросы для проверки

- Чем Context Builder отличается от Prompt Builder?
- Почему не все найденные chunks отправляются LLM?
- Когда полезно объединять соседние chunks?

## Следующие темы

[[RAG/Lost in the Middle|Lost in the Middle]] · [[RAG/Prompt Construction|Prompt Construction]]
