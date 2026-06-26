---
type: concept
area: llm-engineering
status: draft
created: 2026-06-26
updated: 2026-06-26
tags: [vector-database, storage, similarity]
confidence: 0
---

# Vector Database

База данных для хранения и поиска embeddings.

## Простое объяснение

Vector Database — это специальная база данных для хранения и поиска векторов embeddings.

## Интуитивное объяснение

Как библиотека, где книги организованы по смыслу, а не по названию.

## Зачем это нужно

- Быстрый поиск похожих документов
- Основа для RAG систем
- Масштабируемость

## Как это работает

### Примеры
- Pinecone
- Weaviate
- Milvus
- FAISS

### Операции
- Insert embeddings
- Search similarity
- Delete

## Пример

```python
# Псевдокод
db = VectorDB()
db.insert(id="doc1", embedding=embedding)
results = db.search(query_embedding, top_k=5)
```

## Типичные ошибки

- Неправильный размер embeddings
- Плохой индекс
- Забывают обновлять базу

## Связанные темы

- [[Embeddings]] — что хранит
- [[RAG]] — использует для поиска
- [[LLM]] — получает контекст из поиска
- [[AI Agent]] — может работать с базой

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
