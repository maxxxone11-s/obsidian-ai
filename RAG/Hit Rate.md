---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, retrieval]
aliases: [Hit@K, Success Rate]
confidence: high
difficulty: beginner
---

# Hit Rate

## Академическое определение

Hit Rate@K — доля запросов, для которых среди первых `K` результатов найден хотя бы один релевантный документ.

## Инженерное назначение

Метрика быстро показывает, насколько часто retrieval полностью промахивается относительно Ground Truth.

## Причина существования

В pipeline с reranker иногда достаточно, чтобы быстрый retriever сохранил хотя бы одного правильного кандидата для более точного следующего этапа.

## Простое объяснение

Для каждого вопроса проверяется: «Есть ли среди Top-K хотя бы один правильный документ?»

## Как это работает

1. [[RAG/Retrieval|Retriever]] возвращает Top-K.
2. Если пересечение с Ground Truth непустое, `Hit@K = 1`.
3. Иначе `Hit@K = 0`.
4. Значения усредняются по запросам.

## Пример

Если для 80 из 100 запросов в Top-5 есть хотя бы один релевантный документ, `Hit Rate@5 = 0.8`.

## Типичные ошибки

- Путать Hit Rate с Recall.
- Использовать Hit Rate как единственную retrieval-метрику.
- Не указывать значение `K`.

## Связанные темы

[[Machine Learning/Accuracy Precision Recall и F1|Recall]] · [[RAG/Reranking|Reranking]] · [[RAG/Ground Truth|Ground Truth]]

## Вопросы для проверки

- Почему высокий Hit Rate не означает высокий Recall?
- Почему Hit Rate особенно полезен при наличии reranker?

## Следующие темы

[[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]]
