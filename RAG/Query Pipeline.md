---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, query-pipeline, retrieval, generation]
aliases: [Пайплайн запроса, Online RAG Pipeline, Online Pipeline, RAG Query Pipeline]
confidence: high
difficulty: beginner
---

# Query Pipeline

Область: [[RAG/RAG|RAG]]

## Академическое определение

Query Pipeline — онлайн-этап RAG, который обрабатывает пользовательский вопрос, извлекает релевантный контекст из готового индекса и генерирует ответ.

## Инженерное назначение

Он связывает query embedding, retrieval, reranking и LLM generation в последовательность, выполняемую для каждого нового запроса.

## Причина существования

После индексации система всё ещё должна найти контекст именно для текущего вопроса и передать его генератору. Без отдельного онлайн pipeline подготовленная база embeddings не превращается в пользовательский ответ.

## Простое объяснение

Для каждого вопроса создаётся только embedding вопроса. По нему система ищет готовые chunks, уточняет их порядок и передаёт текст лучших chunks в LLM.

## Как это работает

1. Пользователь задаёт вопрос.
2. [[RAG/Orchestrator|Orchestrator]] запускает последовательность обработки.
3. При необходимости [[RAG/Query Transformation|Query Transformation]] уточняет формулировку до построения embedding.
4. Embedding-модель вычисляет embedding итогового запроса.
5. [[RAG/Retrieval|Retriever]] ищет похожие chunks в готовом индексе.
6. [[RAG/Reranking|Reranker]] уточняет порядок кандидатов.
7. [[RAG/Context Construction|Context Builder]] формирует Final Context из SearchResult.
8. [[RAG/Prompt Construction|Prompt Builder]] объединяет инструкции, контекст и вопрос.
9. LLM получает prompt и генерирует ответ.

## Пример

Для вопроса «Сколько дней отпуск?» система вычисляет query embedding, находит в Vector Database chunks из HR policy, reranker выбирает лучшие, а LLM формирует ответ по их тексту.

## Типичные ошибки

- Пересчитывать embeddings всех документов во время запроса.
- Передавать LLM embeddings вместо текста найденных chunks.
- Считать, что RAG во время запроса заново открывает исходный PDF.
- Путать этап retrieval с генерацией ответа.
- Выполнять Query Transformation после построения embedding.

## Связанные темы

[[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Orchestrator|Orchestrator]] · [[RAG/Query Transformation|Query Transformation]] · [[AI Engineering/Embeddings|Embedding]] · [[RAG/Retrieval|Retriever]] · [[RAG/Reranking|Reranker]] · [[RAG/SearchResult|SearchResult]] · [[RAG/Context Construction|Context Builder]] · [[RAG/Prompt Construction|Prompt Builder]]

## Вопросы для проверки

- Какой embedding вычисляется при каждом запросе?
- Почему документы не embedding-ируются заново?
- Что передаётся LLM после retrieval и reranking?
- На каком этапе появляется генерация?
- Почему Query Transformation выполняется до embedding?

## Следующие темы

[[RAG/Orchestrator|Orchestrator]] · [[RAG/Query Transformation|Query Transformation]] · [[RAG/Production RAG Pipeline|Production RAG Pipeline]] · [[RAG/Evaluation|Evaluation]]
