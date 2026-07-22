---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, production, architecture, pipeline]
aliases: [Production RAG, Полный жизненный цикл документа в RAG, Production RAG Pipeline Architecture, RAG Pipeline]
confidence: high
difficulty: advanced
---

# Production RAG Pipeline

Область: [[RAG/RAG|RAG]]

## Академическое определение

Production RAG Pipeline — архитектура полного жизненного цикла RAG, разделённая на независимый Ingestion Pipeline и онлайн Query Pipeline, состоящие из компонентов с одной инженерной ответственностью и координируемые orchestrator.

## Инженерное назначение

Архитектура отделяет подготовку документов от критичного по задержке пути запроса и позволяет независимо заменять, тестировать и масштабировать loader, retriever, reranker, context builder, prompt builder и LLM.

## Причина существования

Единый монолит, который при каждом вопросе заново обрабатывает документы и смешивает retrieval, context construction и generation, был бы медленным, сильно связанным и трудным для тестирования. Разделение ответственности устраняет повторную работу и локализует изменения.

## Простое объяснение

Система заранее готовит searchable records, а при запросе последовательно вызывает независимые компоненты. Каждый компонент выполняет только свою работу, а orchestrator управляет порядком.

## Как это работает

Первая стадия — [[RAG/Ingestion Pipeline|Ingestion Pipeline]]:

`Documents → Loader → Cleaning → Chunking → Metadata → Embeddings → Indexing → Vector Database`

Вторая стадия — [[RAG/Query Pipeline|Query Pipeline]]:

`Question → Orchestrator → Query Transformation → Query Embedding → Retriever → Reranker → Context Builder → Prompt Builder → LLM → Answer`

Документные embeddings создаются во время индексации, а query embedding — для каждого нового вопроса.

## Пример

Компания заранее индексирует `HR_policy.pdf`. Когда сотрудник спрашивает о длительности отпуска, система не открывает PDF заново: она ищет по сохранённым embeddings, извлекает соответствующие chunks и передаёт их LLM.

В коде метод `RAGPipeline.answer()` может последовательно вызвать `retrieve()`, `rerank()`, `build_context()`, `build_prompt()` и `generate()`, не реализуя внутреннюю логику этих операций самостоятельно.

## Типичные ошибки

- Смешивать Indexing Pipeline и Query Pipeline в один повторяемый процесс.
- Считать, что LLM участвует в чтении, chunking или индексации документов.
- Пересчитывать embeddings всей базы при каждом запросе.
- Считать, что RAG онлайн читает исходные файлы вместо готового индекса.
- Помещать всю бизнес-логику в один pipeline-класс.
- Нарушать Single Responsibility Principle и заставлять retriever напрямую вызывать LLM.

## Связанные темы

[[RAG/Ingestion Pipeline|Ingestion Pipeline]] · [[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Orchestrator|Orchestrator]] · [[RAG/Query Transformation|Query Transformation]] · [[RAG/SearchResult|SearchResult]] · [[RAG/Context Construction|Context Builder]] · [[RAG/Prompt Construction|Prompt Builder]] · [[AI Engineering/Vector Database|Vector Database]]

## Вопросы для проверки

- Почему Production RAG разделён на две стадии?
- Какие операции выполняются только заранее?
- Что вычисляется заново для каждого вопроса?
- На каких этапах участвует LLM?
- Почему retriever не должен напрямую вызывать LLM?
- Какие преимущества даёт разделение компонентов?

## Следующие темы

[[RAG/Prompt Construction|Prompt Construction]] · [[RAG/Context Construction|Context Construction]] · [[RAG/Lost in the Middle|Lost in the Middle]]
