---
type: concept
area: RAG
status: learning
created: 2026-07-11
updated: 2026-07-11
tags: [rag, indexing, ingestion]
aliases: [Пайплайн индексации, Document Indexing Pipeline]
confidence: medium
difficulty: intermediate
---

# Indexing Pipeline

## Академическое определение

Indexing Pipeline — офлайн-этап RAG, который преобразует исходные документы в индексированные chunks и сохраняет их embeddings для будущего поиска.

## Инженерное назначение

Он заранее выполняет дорогую подготовку базы знаний, чтобы пользовательский запрос работал только с готовым индексом и не перерабатывал всю коллекцию документов.

## Причина существования

Перечитывать и повторно embedding-ировать миллионы документов при каждом вопросе невозможно по времени и стоимости. Подготовку документов нужно отделить от обслуживания запросов.

## Простое объяснение

Сначала документы один раз подготавливаются: из них достают текст, делят его на chunks, превращают chunks в embeddings и сохраняют в Vector Database.

## Как это работает

1. [[RAG/Document Loader|Document Loader]] извлекает текст из источника.
2. Chunking делит текст на самостоятельные смысловые fragments.
3. Embedding-модель вычисляет вектор для каждого chunk.
4. [[AI Engineering/Vector Database|Vector Database]] сохраняет vectors, chunks и метаданные.
5. При добавлении или изменении документов соответствующая часть индекса обновляется.

LLM-генератор в этой последовательности не участвует.

## Пример

Ночью система обрабатывает новые корпоративные PDF по цепочке `Documents → Loader → Chunking → Embeddings → Vector Database`. На следующий день вопросы используют уже готовый индекс.

## Типичные ошибки

- Запускать полную индексацию при каждом вопросе пользователя.
- Считать индексацию этапом генерации ответа.
- Создавать один embedding для большого документа вместо его chunks.
- Не обновлять индекс после изменения источника.

## Связанные темы

[[RAG/Document Loader|Document Loader]] · [[RAG/Chunk|Chunk]] · [[AI Engineering/Embeddings|Embedding]] · [[AI Engineering/Vector Database|Vector Database]] · [[RAG/Query Pipeline|Query Pipeline]]

## Вопросы для проверки

- Какие этапы входят в Indexing Pipeline?
- Почему индексация выполняется заранее?
- Участвует ли LLM-генератор в индексации?
- Когда embeddings документов нужно пересчитывать?

## Следующие темы

[[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Production RAG Pipeline|Production RAG Pipeline]]
