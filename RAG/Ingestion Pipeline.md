---
type: concept
area: RAG
status: learned
created: 2026-07-12
updated: 2026-07-12
tags: [rag, ingestion, indexing, document-processing]
aliases: [Document Processing Pipeline, Document Ingestion Pipeline]
confidence: high
difficulty: intermediate
---

# Ingestion Pipeline

Область: [[RAG/RAG|RAG]]

## Академическое определение

Ingestion Pipeline — независимый процесс приёма, очистки, разбиения, обогащения metadata, embedding-обработки и записи документов в поисковый индекс RAG.

## Инженерное назначение

Pipeline превращает исходные PDF, DOCX, HTML и другие источники в версионируемые searchable records, пригодные для быстрого retrieval и точечного обновления.

## Причина существования

Retriever не работает непосредственно с исходным файлом. Документ необходимо извлечь, очистить, разбить на chunks, связать с metadata и заранее представить в форме, поддерживаемой поисковым индексом.

## Простое объяснение

Ingestion Pipeline превращает обычные документы в подготовленные данные для поиска.

## Как это работает

1. [[RAG/Document Loader|Loader]] извлекает содержимое источника.
2. Текст очищается и нормализуется.
3. Документ разбивается на [[RAG/Chunk|chunks]].
4. К chunks добавляется metadata источника.
5. Embedding-модель создаёт vectors.
6. [[RAG/Indexing Pipeline|Indexing Pipeline]] записывает или обновляет records в Vector Database.

## Пример

При обновлении одного PDF система повторно обрабатывает и индексирует только records этого документа, а не всю коллекцию.

## Типичные ошибки

- Путать Ingestion Pipeline с онлайн [[RAG/Query Pipeline|Query Pipeline]].
- Полностью переиндексировать коллекцию при изменении одного документа.
- Хранить только текст без source metadata.
- Считать Ingestion Pipeline точным синонимом Indexing Pipeline, игнорируя loading, cleaning и metadata enrichment.

## Связанные темы

[[RAG/Document Loader|Document Loader]] · [[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Chunk|Chunk]] · [[AI Engineering/Embeddings|Embedding]] · [[AI Engineering/Vector Database|Vector Database]]

## Вопросы для проверки

- Чем Ingestion Pipeline отличается от Query Pipeline?
- Чем ingestion шире indexing?
- Почему для chunks необходимо сохранять metadata?

## Следующие темы

[[RAG/Production RAG Pipeline|Production RAG Pipeline]]
