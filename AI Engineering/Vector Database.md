---
type: concept
area: RAG
status: learning
created: 2026-06-26
updated: 2026-07-11
tags: [rag, vector-database, storage, similarity]
aliases: [Векторная база данных, Vector DB]
confidence: medium
difficulty: intermediate
---

# Vector Database

## Академическое определение

Vector Database — система хранения и индексирования векторных представлений, оптимизированная для поиска объектов по близости их embeddings.

## Инженерное назначение

В RAG Vector Database хранит embeddings заранее подготовленных chunks вместе с идентификаторами и метаданными, а во время запроса возвращает chunks, ближайшие к embedding вопроса.

## Причина существования

При каждом вопросе пересчитывать embeddings всей коллекции и сравнивать документы с нуля слишком дорого. Заранее сохранённый векторный индекс позволяет отделить подготовку документов от онлайн-поиска.

## Простое объяснение

Это библиотека, в которой fragments организованы по близости смысла. Вопрос превращается в вектор, после чего база находит наиболее близкие сохранённые векторы и возвращает связанные с ними chunks.

## Как это работает

1. Во время [[RAG/Indexing Pipeline|Indexing Pipeline]] каждый chunk получает embedding.
2. В базе сохраняются embedding, текст chunk, идентификатор и метаданные.
3. Во время [[RAG/Query Pipeline|Query Pipeline]] для вопроса вычисляется embedding.
4. База выполняет similarity search и возвращает ближайшие записи.
5. Найденные chunks передаются следующим этапам RAG; сами embeddings не являются контекстом для LLM.

## Пример

```python
# Псевдокод
db = VectorDB()
db.insert(id="doc1", text=chunk, embedding=embedding)
results = db.search(query_embedding, top_k=5)
```

Примеры инструментов: Pinecone, Weaviate, Milvus, FAISS, pgvector и Qdrant.

## Типичные ошибки

- Пересчитывать embeddings документов при каждом пользовательском запросе.
- Хранить embedding без связи с исходным chunk и его метаданными.
- Использовать несовместимые embedding-модели для документов и запросов.
- Считать, что Vector Database генерирует ответ или передаёт LLM векторы вместо текста.
- Не обновлять индекс после изменения документов.

## Связанные темы

[[AI Engineering/Embeddings|Embedding]] · [[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Retrieval|Retrieval]] · [[AI Engineering/RAG|RAG]]

## Вопросы для проверки

- Что именно хранит Vector Database в RAG?
- Почему embeddings документов вычисляются заранее?
- Что база возвращает после similarity search?
- Чем роль Vector Database отличается от роли LLM?

## Следующие темы

[[RAG/Indexing Pipeline|Indexing Pipeline]] · [[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Retrieval|Retrieval]]
