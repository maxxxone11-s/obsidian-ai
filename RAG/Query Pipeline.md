---
type: concept
area: RAG
status: learning
created: 2026-07-11
updated: 2026-07-11
tags: [rag, query-pipeline, retrieval, generation]
aliases: [Пайплайн запроса, Online RAG Pipeline]
confidence: medium
difficulty: intermediate
---

# Query Pipeline

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
2. Embedding-модель вычисляет embedding вопроса.
3. [[RAG/Retrieval|Retriever]] ищет похожие chunks в готовом индексе.
4. [[RAG/Reranking|Reranker]] уточняет порядок кандидатов.
5. Лучшие chunks формируют контекст.
6. LLM получает вопрос и контекст и генерирует ответ.

## Пример

Для вопроса «Сколько дней отпуск?» система вычисляет query embedding, находит в Vector Database chunks из HR policy, reranker выбирает лучшие, а LLM формирует ответ по их тексту.

## Типичные ошибки

- Пересчитывать embeddings всех документов во время запроса.
- Передавать LLM embeddings вместо текста найденных chunks.
- Считать, что RAG во время запроса заново открывает исходный PDF.
- Путать этап retrieval с генерацией ответа.

## Связанные темы

[[RAG/Indexing Pipeline|Indexing Pipeline]] · [[AI Engineering/Embeddings|Embedding]] · [[RAG/Retrieval|Retrieval]] · [[RAG/Reranking|Reranking]] · [[RAG/Faithfulness|Faithfulness]]

## Вопросы для проверки

- Какой embedding вычисляется при каждом запросе?
- Почему документы не embedding-ируются заново?
- Что передаётся LLM после retrieval и reranking?
- На каком этапе появляется генерация?

## Следующие темы

[[RAG/Production RAG Pipeline|Production RAG Pipeline]] · [[RAG/Evaluation|Evaluation]]
