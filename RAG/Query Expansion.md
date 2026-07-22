---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, retrieval, query-transformation, query-expansion]
aliases: [Query Enrichment]
confidence: high
difficulty: intermediate
---

# Query Expansion

Область: [[RAG/RAG|RAG]]

## Академическое определение

Query Expansion — техника [[RAG/Query Transformation|Query Transformation]], расширяющая исходный запрос связанными терминами, синонимами и расшифровками без удаления первоначальной формулировки.

## Инженерное назначение

Техника повышает вероятность найти документы, которые описывают ту же концепцию другими словами или используют полные названия вместо сокращений.

## Причина существования

Лексика пользователя и документации может различаться. Один короткий термин не всегда создаёт embedding, охватывающий все релевантные формулировки.

## Простое объяснение

Query Expansion сохраняет исходный запрос и добавляет к нему связанные понятия, чтобы поиск видел больше способов выразить тот же смысл.

## Как это работает

1. Получает исходный запрос.
2. Определяет релевантные синонимы, расшифровки и связанные термины.
3. Добавляет их к исходной формулировке.
4. Для расширенного запроса строится embedding.
5. Retriever выполняет semantic search.

## Пример

Запрос `JWT` расширяется до `JWT, JSON Web Token, Authentication, Bearer Token`.

## Типичные ошибки

- Добавлять слишком много терминов и размывать query embedding.
- Включать понятия, меняющие исходное намерение.
- Удалять исходный запрос вместо его дополнения.
- Путать Expansion с [[RAG/Query Rewrite|Query Rewrite]].

## Связанные темы

[[RAG/Query Transformation|Query Transformation]] · [[RAG/Query Rewrite|Query Rewrite]] · [[AI Engineering/Embeddings|Embedding]] · [[RAG/Retrieval|Retriever]]

## Вопросы для проверки

- Чем Query Expansion отличается от Query Rewrite?
- Почему синонимы способны улучшить semantic search?
- Почему чрезмерное расширение ухудшает retrieval?

## Следующие темы

[[RAG/HyDE|HyDE]]
