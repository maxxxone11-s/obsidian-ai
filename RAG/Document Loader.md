---
type: concept
area: RAG
status: learning
created: 2026-07-11
updated: 2026-07-11
tags: [rag, ingestion, loader]
aliases: [Loader, Загрузчик документов]
confidence: medium
difficulty: beginner
---

# Document Loader

## Академическое определение

Document Loader — компонент ingestion-части RAG, который читает внешний источник данных и преобразует его содержимое в текстовое представление для дальнейшей обработки.

## Инженерное назначение

Loader создаёт единый вход для разных источников: PDF, DOCX, HTML, Markdown, TXT, Notion, Confluence и Google Docs.

## Причина существования

Chunking и embedding-модель работают не с интерфейсом внешней системы или контейнером файла, а с извлечённым содержимым. Без Loader каждый источник пришлось бы обрабатывать внутри остальных этапов pipeline.

## Простое объяснение

Loader открывает источник и достаёт из него текст. На этом этапе ещё не создаются ни chunks, ни embeddings.

## Как это работает

1. Получает ссылку, файл или подключение к источнику.
2. Читает данные в формате источника.
3. Извлекает текстовое содержимое.
4. Передаёт текст этапу chunking.

## Пример

Loader читает `HR_policy.pdf` на 100 страниц и передаёт извлечённый текст chunker, который затем разбивает политику компании на поисковые единицы.

## Типичные ошибки

- Считать, что Loader сразу создаёт embeddings.
- Передавать PDF напрямую в Vector Database без извлечения и разбиения текста.
- Смешивать чтение источника с генерацией ответа LLM.

## Связанные темы

[[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Chunk|Chunk]] · [[AI Engineering/Embeddings|Embedding]]

## Вопросы для проверки

- Что Loader возвращает следующему этапу?
- Почему Loader стоит перед chunking?
- Создаёт ли Loader embedding документа?

## Следующие темы

[[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Chunk|Chunk]]
