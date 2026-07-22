---
type: module_plan
area: Vector Databases
status: learning
created: 2026-07-12
updated: 2026-07-17
tags: [vector-databases, module-plan]
---

# Vector Databases Plan

## Цель модуля

Научиться понимать устройство векторного поиска, выбирать подходящую метрику и индекс, работать с pgvector, Qdrant и Pinecone, оценивать производительность retrieval и сопровождать Vector Database в production.

## Предварительные знания

- [[AI Engineering/Embeddings|Embedding]]
- [[Machine Learning/Mathematics/Вектор|Вектор]]
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- [[RAG/Retrieval|Retrieval]]
- [[RAG/Chunk|Chunk]]
- [[Python Backend/PostgreSQL|PostgreSQL]]

## Learning Path

1. Основы векторного поиска
2. Similarity Search
3. Индексы
4. pgvector
5. Qdrant
6. Pinecone
7. Производительность
8. RAG и Vector DB
9. Production
10. Практика

## Часть 1. Основы векторного поиска

status: not_started

Цель: связать embedding-пространство, геометрию vectors и метрики близости с задачей семантического поиска.

Темы:

- [[AI Engineering/Embeddings|Embedding]]
- Почему обычная SQL БД не подходит для семантического поиска
- [[Machine Learning/Mathematics/Вектор|Вектор]]
- [[Transformers/Embedding Space|Embedding Space]]
- Близость vectors
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- Euclidean Distance
- Dot Product
- Выбор метрики под модель и индекс

## Часть 2. Similarity Search

status: learned

Цель: понять различие точного и приближённого поиска и компромисс между качеством, скоростью и стоимостью.

Темы:

- [[Vector Databases/Exact Search|Exact Search]]
- [[Vector Databases/Approximate Nearest Neighbor (ANN)|Approximate Nearest Neighbor (ANN)]]
- Почему полный перебор плохо масштабируется
- [[RAG/Top-K Retrieval|Top-K Search]]
- Radius Search
- Recall vs Speed
- Внутренний lifecycle поискового запроса

## Часть 3. Индексы

status: learning

Цель: понять, как индекс сокращает пространство поиска и какие параметры управляют качеством ANN.

Темы:

- Зачем нужен vector index
- [[Vector Databases/HNSW|HNSW]]
- Граф ближайших соседей
- Построение HNSW
- [[Vector Databases/Параметр efConstruction|efConstruction]]
- [[Vector Databases/Параметр efSearch|efSearch]]
- [[Vector Databases/Параметр M в HNSW|параметр M]]
- [[Vector Databases/Жизненный цикл параметров HNSW|Жизненный цикл параметров HNSW]]
- IVF
- Почему HNSW часто выбирают для современных систем

## Часть 4. pgvector

status: not_started

Цель: научиться хранить и искать embeddings в PostgreSQL.

Темы:

- Что такое pgvector
- Тип `vector`
- Хранение embedding и metadata
- Создание таблицы
- Создание индекса
- Поиск ближайших соседей
- Cosine Search
- L2 Search
- Inner Product Search
- Когда PostgreSQL достаточно

## Часть 5. Qdrant

status: not_started

Цель: изучить специализированную Vector Database с payload filtering и HNSW.

Темы:

- Архитектура Qdrant
- Collections
- Points
- Payload
- Фильтрация по Payload
- HNSW внутри Qdrant
- Hybrid Search
- Batch Insert
- Upsert
- Delete

## Часть 6. Pinecone

status: not_started

Цель: понять managed-подход к Vector Database и его эксплуатационные компромиссы.

Темы:

- Архитектура Pinecone
- Namespaces
- Metadata
- Serverless Index
- Pods
- Масштабирование
- Когда Pinecone удобнее Qdrant

## Часть 7. Производительность

status: not_started

Цель: оценивать память, latency, throughput и стоимость vector workloads.

Темы:

- Размер embedding
- Память для embedding размерности 1536
- Размерность vectors
- Кэширование
- Batch Embedding
- Batch Search
- Latency
- Throughput

## Часть 8. RAG и Vector DB

status: not_started

Цель: встроить Vector Database в полный retrieval pipeline и понимать влияние качества поиска на ответ LLM.

Темы:

- [[RAG/Chunk|Chunking]]
- Chunk Size
- [[RAG/Chunk Overlap|Overlap]]
- Metadata
- [[RAG/Retrieval|Retrieval Pipeline]]
- [[RAG/Top-K Retrieval|Top-K Retrieval]]
- [[RAG/Reranking|Re-ranking]]
- [[RAG/Context Construction|Context Building]]
- Почему плохой retrieval ломает LLM

## Часть 9. Production

status: not_started

Цель: научиться безопасно обновлять индекс, мигрировать embedding-модели и измерять качество поиска.

Темы:

- Обновление embeddings
- Версионирование embeddings
- Soft Delete
- Reindex
- Миграции
- Мониторинг качества поиска
- Recall Evaluation
- A/B-тестирование retrieval

## Часть 10. Практика

status: learning

Цель: реализовать полный путь от создания embeddings до работающего retrieval и мини-RAG.

Практические работы:

- Поднять pgvector
- Проиндексировать документы
- Сгенерировать embeddings
- Загрузить vectors и metadata в БД
- Реализовать поиск похожих документов
- Написать собственный Similarity Search
- Собрать мини-RAG на pgvector
- Собрать мини-RAG на Qdrant
- Сравнить pgvector и Qdrant

## Инженерные вопросы модуля

- Когда exact search лучше ANN?
- Как выбирать similarity metric?
- Как параметры HNSW влияют на Recall, latency и memory?
- Когда достаточно pgvector, а когда нужна специализированная Vector Database?
- Как обновлять embedding-модель без повреждения production retrieval?
- Как измерять качество поиска независимо от качества LLM?

## Результат модуля

После завершения модуля должна получиться практическая система, которая индексирует документы, выполняет vector search через pgvector и Qdrant, измеряет retrieval quality и может использоваться внутри [[RAG/Production RAG Pipeline|Production RAG Pipeline]].
