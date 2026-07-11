---
type: concept
area: RAG
status: learning
created: 2026-07-11
updated: 2026-07-11
tags: [rag, production, architecture, pipeline]
aliases: [Production RAG, Полный жизненный цикл документа в RAG]
confidence: medium
difficulty: intermediate
---

# Production RAG Pipeline

## Академическое определение

Production RAG Pipeline — архитектура полного жизненного цикла RAG, разделённая на предварительную индексацию базы знаний и онлайн-обработку пользовательских запросов.

## Инженерное назначение

Архитектура отделяет подготовку документов от критичного по задержке пути запроса, позволяя переиспользовать индекс, масштабировать поиск и подключать LLM только там, где требуется генерация.

## Причина существования

Единый pipeline, который при каждом вопросе заново читает документы, разбивает их и вычисляет embeddings, был бы слишком медленным и дорогим. Разделение жизненных циклов устраняет повторную работу.

## Простое объяснение

Система сначала заранее готовит библиотеку документов, а затем при каждом вопросе ищет в этой библиотеке нужные fragments и только после этого вызывает LLM.

## Как это работает

Первая стадия — [[RAG/Indexing Pipeline|Indexing Pipeline]]:

`Documents → Loader → Chunking → Embeddings → Vector Database`

Вторая стадия — [[RAG/Query Pipeline|Query Pipeline]]:

`Question → Orchestrator → Query Transformation → Query Embedding → Retriever → Reranker → Context → LLM → Answer`

Документные embeddings создаются во время индексации, а query embedding — для каждого нового вопроса.

## Пример

Компания заранее индексирует `HR_policy.pdf`. Когда сотрудник спрашивает о длительности отпуска, система не открывает PDF заново: она ищет по сохранённым embeddings, извлекает соответствующие chunks и передаёт их LLM.

## Типичные ошибки

- Смешивать Indexing Pipeline и Query Pipeline в один повторяемый процесс.
- Считать, что LLM участвует в чтении, chunking или индексации документов.
- Пересчитывать embeddings всей базы при каждом запросе.
- Считать, что RAG онлайн читает исходные файлы вместо готового индекса.

## Связанные темы

[[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Document Loader|Document Loader]] · [[RAG/Orchestrator|Orchestrator]] · [[RAG/Query Transformation|Query Transformation]] · [[AI Engineering/Vector Database|Vector Database]] · [[RAG/Evaluation|Evaluation]]

## Вопросы для проверки

- Почему Production RAG разделён на две стадии?
- Какие операции выполняются только заранее?
- Что вычисляется заново для каждого вопроса?
- На каких этапах участвует LLM?

## Следующие темы

[[RAG/Orchestrator|Orchestrator]] · [[RAG/Query Transformation|Query Transformation]] · [[Prompt Construction]] · [[Context Injection]] · [[Citation]] · [[Monitoring]]
