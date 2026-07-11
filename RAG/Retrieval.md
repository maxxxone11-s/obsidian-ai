---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, retrieval, semantic-search]
aliases: [Retriever, Semantic Retrieval]
confidence: high
difficulty: beginner
---

# Retrieval

## Академическое определение

Retrieval — подсистема RAG, которая сопоставляет пользовательский запрос с индексом документов и формирует ранжированный набор наиболее релевантных кандидатов. В hybrid-архитектуре это не одна функция, а последовательность semantic search, keyword search, fusion и отбора Top-K.

## Инженерное назначение

Retrieval быстро сокращает большую базу знаний до небольшого набора chunks, которые потенциально содержат информацию для ответа.

## Причина существования

LLM не может эффективно анализировать всю базу знаний в одном запросе из-за ограниченного [[LLM Engineering/Context Window|Context Window]], стоимости и шума. Система должна выбрать релевантный контекст до генерации.

## Простое объяснение

Retriever превращает вопрос в embedding, сравнивает его с embeddings документов, сортирует результаты и возвращает наиболее подходящие chunks. Сам ответ он не генерирует.

## Как это работает

1. Запрос преобразуется той же embedding-моделью, которой индексировались документы.
2. Вектор запроса сравнивается с векторами документов.
3. Кандидаты получают similarity scores.
4. При Hybrid Search параллельно формируется keyword-выдача.
5. [[Reciprocal Rank Fusion (RRF)|RRF]] или другой fusion-алгоритм объединяет ранжированные списки.
6. Результаты сортируются и фильтруются.
7. [[RAG/Top-K Retrieval|Top-K Retrieval]] возвращает ограниченный набор chunks для следующего этапа.

## Пример

Для вопроса «Как установить PostgreSQL?» retriever вычисляет сходство запроса с индексом базы знаний и возвращает chunks с инструкциями по установке.

## Типичные ошибки

- Использовать разные embedding-модели для документов и запросов.
- Считать, что retriever отвечает на вопрос пользователя.
- Сводить Retrieval к одной операции vector similarity search, игнорируя остальные компоненты hybrid pipeline.
- Передавать в LLM все найденные документы без отбора.
- Называть результатом поиска «Top-K embeddings», хотя дальше передаются соответствующие chunks.

## Связанные темы

[[AI Engineering/Embeddings|Embedding]] · [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]] · [[RAG/Hybrid Search|Hybrid Search]] · [[Reciprocal Rank Fusion (RRF)|RRF]] · [[RAG/Top-K Retrieval|Top-K Retrieval]] · [[RAG/Reranking|Reranking]]

## Вопросы для проверки

- Почему запрос и документы должны использовать совместимое embedding-пространство?
- Что делает retriever после вычисления similarity?
- Из каких этапов может состоять hybrid retrieval pipeline?
- Почему retriever не генерирует ответ?

## Следующие темы

[[RAG/Top-K Retrieval|Top-K Retrieval]] · [[RAG/Hybrid Search|Hybrid Search]]
