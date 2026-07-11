---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, context]
aliases: [Context Quality Precision]
confidence: high
difficulty: intermediate
---

# Context Precision

## Академическое определение

Context Precision — метрика качества итогового контекста, оценивающая долю или ранговое расположение действительно полезной информации среди chunks, переданных генератору.

## Инженерное назначение

Метрика показывает чистоту контекста после retrieval, фильтрации и reranking и помогает обнаруживать лишний шум перед LLM.

## Причина существования

Даже работающий retriever может передать много нерелевантных chunks, увеличивая стоимость, расход Context Window и вероятность ошибок генерации.

## Простое объяснение

Context Precision показывает, насколько полезным и чистым оказался контекст, который получила модель.

## Как это работает

1. Фиксируется список chunks, переданных LLM.
2. Для вопроса определяется полезность каждого chunk.
3. Оценивается доля полезных chunks и, в зависимости от реализации метрики, их положение в списке.
4. Результат используется для настройки Top-K, reranking и фильтрации.

## Пример

Из пяти переданных chunks только два содержат информацию, полезную для ответа. Context Precision будет низким, даже если эти два chunk правильные.

## Типичные ошибки

- Путать Context Precision с Retrieval Precision.
- Считать, что большой Top-K всегда улучшает ответ.
- Игнорировать порядок chunks, когда используемая реализация метрики его учитывает.

## Связанные темы

[[RAG/Context Recall|Context Recall]] · [[RAG/Top-K Retrieval|Top-K Retrieval]] · [[Machine Learning/Accuracy Precision Recall и F1|Retrieval Precision]]

## Вопросы для проверки

- Что оценивает Context Precision?
- Почему большой Top-K может ухудшить Context Precision?

## Следующие темы

[[RAG/Context Recall|Context Recall]]
