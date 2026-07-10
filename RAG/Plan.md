---
type: module_plan
area: RAG
status: not_started
tags:
  - rag
  - module-plan
---

# RAG Plan

## Module Goal

Научиться проектировать, реализовывать и оценивать production-подобные RAG-системы: от подготовки документов и embeddings до retrieval, reranking, generation, evaluation, monitoring и advanced-подходов.

## Learning Path

1. Почему появился RAG
2. Embeddings
3. Chunking
4. Vector Database
5. Retrieval
6. Hybrid Search
7. Reranking
8. Generation
9. Evaluation
10. Production RAG
11. Advanced RAG
12. Финальный проект

## Topics

### 1. Почему появился RAG

status: not_started

Коротко: понять ограничения знаний LLM, причины hallucinations и место RAG среди способов адаптации модели.

Related concepts:

- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Transformers/Разделение ролей LLM и RAG|Разделение ролей LLM и RAG]]
- [[LLM Engineering/Context Window|Context Window]]
- [[LLM Engineering/Production Pipeline LLM-приложения|Production Pipeline LLM-приложения]]

Topics:

- Почему LLM забывают знания
- Контекстное окно
- Hallucinations
- Fine-tuning vs RAG
- Когда нужен RAG, а когда нет
- Архитектура RAG целиком

### 2. Embeddings

status: not_started

Коротко: понять, как смысл представляется в векторном пространстве и используется для поиска похожих документов.

Prerequisites:

- Почему появился RAG

Related concepts:

- [[Transformers/Embedding Space|Embedding Space]]
- [[Machine Learning/Mathematics/Вектор|Вектор]]
- [[Machine Learning/Mathematics/Размерность вектора|Размерность вектора]]
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- [[Machine Learning/Mathematics/Скалярное произведение|Скалярное произведение]]

Topics:

- Что такое embedding
- Почему embedding — это не просто вектор
- Семантическое пространство
- Косинусное сходство
- Euclidean Distance
- Dot Product
- Почему похожие предложения оказываются рядом
- Размерность embedding
- Как создаются embeddings

### 3. Chunking

status: not_started

Коротко: научиться делить документы на поисковые единицы с учётом структуры, смысла и ограничений retrieval.

Prerequisites:

- Embeddings

Related concepts:

- [[LLM Engineering/Context Window|Context Window]]
- [[LLM Engineering/Token Counting|Token Counting]]

Topics:

- Почему нельзя хранить документ целиком
- Chunk Size
- Chunk Overlap
- Sliding Window
- Recursive Chunking
- Semantic Chunking
- Markdown Chunking
- Code Chunking
- Таблицы
- PDF
- Реальные ошибки chunking

### 4. Vector Database

status: not_started

Коротко: изучить минимально необходимую для RAG часть хранения embeddings и приближённого поиска ближайших соседей.

Prerequisites:

- Embeddings
- Chunking

Related concepts:

- [[Python Backend/PostgreSQL|PostgreSQL]]
- [[Python Backend/SQL|SQL]]

Topics:

- Почему обычного SQL недостаточно для векторного поиска
- ANN Search
- HNSW
- IVF
- pgvector
- Qdrant
- Pinecone

### 5. Retrieval

status: not_started

Коротко: научиться извлекать релевантные документы и управлять полнотой, точностью и ограничениями выдачи.

Prerequisites:

- Embeddings
- Vector Database

Related concepts:

- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- [[Machine Learning/Accuracy Precision Recall и F1|Accuracy Precision Recall и F1]]

Topics:

- Similarity Search
- Top-K
- Threshold
- Metadata Filtering
- Dense Retrieval
- Sparse Retrieval
- BM25
- Query Expansion
- Multi Query Retrieval

### 6. Hybrid Search

status: not_started

Коротко: объединить семантический и лексический поиск, когда одного embedding-поиска недостаточно.

Prerequisites:

- Retrieval

Topics:

- Dense Search
- Sparse Search
- BM25
- Hybrid Search
- Reciprocal Rank Fusion (RRF)
- Когда использовать каждый подход

### 7. Reranking

status: not_started

Коротко: научиться повторно ранжировать найденные документы более точной моделью перед передачей контекста LLM.

Prerequisites:

- Retrieval
- Hybrid Search

Related concepts:

- [[Transformers/Index|Transformers]]

Topics:

- Cross Encoder
- Bi Encoder
- Reranker
- Late Interaction
- ColBERT
- Top-K → Rerank → Top-N

### 8. Generation

status: not_started

Коротко: соединить retrieval с LLM, сформировать контекст и обеспечить проверяемые ссылки на источники.

Prerequisites:

- Retrieval
- Reranking

Related concepts:

- [[LLM Engineering/Prompt Engineering|Prompt Engineering]]
- [[LLM Engineering/Prompt Templates|Prompt Templates]]
- [[LLM Engineering/Context Window|Context Window]]
- [[LLM Engineering/Memory Management|Memory Management]]

Topics:

- Prompt Construction
- Context Injection
- Citation
- Source Attribution
- Context Compression
- Lost in the Middle
- Long Context

### 9. Evaluation

status: not_started

Коротко: измерять качество retrieval и ответа, отделяя нахождение документов от генерации по найденному контексту.

Prerequisites:

- Retrieval
- Generation

Related concepts:

- [[Machine Learning/Accuracy Precision Recall и F1|Accuracy Precision Recall и F1]]

Topics:

- Recall
- Precision
- MRR
- NDCG
- Hit Rate
- Faithfulness
- Groundedness
- Answer Relevancy

### 10. Production RAG

status: not_started

Коротко: построить надёжные ingestion, indexing и query pipelines с обновлениями, cache, monitoring и контролем стоимости.

Prerequisites:

- Chunking
- Vector Database
- Retrieval
- Generation
- Evaluation

Related concepts:

- [[LLM Engineering/Production Pipeline LLM-приложения|Production Pipeline LLM-приложения]]
- [[LLM Engineering/Cost Optimization|Cost Optimization]]
- [[Python Backend/FastAPI|FastAPI]]
- [[Python Backend/Redis|Redis]]

Topics:

- Indexing Pipeline
- Ingestion Pipeline
- Embedding Cache
- Query Cache
- Versioning
- Incremental Updates
- Monitoring
- Cost Optimization

### 11. Advanced RAG

status: not_started

Коротко: изучить современные стратегии извлечения и организации контекста для сложных документов, запросов и agent workflows.

Prerequisites:

- Production RAG

Related concepts:

- [[AI Agents/Index|AI Agents]]

Topics:

- Parent Document Retrieval
- Multi Vector Retrieval
- Self Query Retrieval
- Graph RAG
- Agentic RAG
- RAPTOR
- Contextual Retrieval

### 12. Финальный проект

status: not_started

Коротко: объединить ingestion, chunking, indexing, retrieval, reranking, generation, evaluation и production-наблюдаемость в одной production-подобной RAG-системе.

Prerequisites:

- Production RAG
- Advanced RAG

## Practical Work

- Создать embeddings и исследовать их размерность.
- Реализовать поиск похожих документов.
- Сравнить стратегии chunking на Markdown, PDF, таблицах и коде.
- Подобрать `Chunk Size` и `Chunk Overlap` на измеримом наборе запросов.
- Проиндексировать документы в pgvector или Qdrant.
- Реализовать dense, sparse и hybrid retrieval.
- Объединить результаты через Reciprocal Rank Fusion.
- Реализовать pipeline `Top-K → Rerank → Top-N`.
- Собрать generation prompt с citations и source attribution.
- Оценить retrieval через Recall, Precision, MRR, NDCG и Hit Rate.
- Оценить generation через Faithfulness, Groundedness и Answer Relevancy.
- Реализовать indexing и ingestion pipelines.
- Добавить cache, versioning, incremental updates и monitoring.
- Построить production-подобный финальный RAG-проект.

## Dependencies

- [[LLM Engineering/Index|LLM Engineering]]
- [[Transformers/Index|Transformers]]
- [[Machine Learning/Index|Machine Learning]]
- [[Python Backend/Index|Python Backend]]
- [[AI Agents/Index|AI Agents]]

## Future KNOWLEDGE_EXPORT Targets

- RAG
- Архитектура RAG
- Hallucinations
- Fine-tuning vs RAG
- Embedding
- Semantic Space
- Euclidean Distance
- Dot Product
- Chunking
- Chunk Size
- Chunk Overlap
- Recursive Chunking
- Semantic Chunking
- Markdown Chunking
- Code Chunking
- ANN Search
- HNSW
- IVF
- pgvector
- Qdrant
- Pinecone
- Similarity Search
- Top-K
- Metadata Filtering
- Dense Retrieval
- Sparse Retrieval
- BM25
- Query Expansion
- Multi Query Retrieval
- Hybrid Search
- Reciprocal Rank Fusion
- Cross Encoder
- Bi Encoder
- Reranker
- Late Interaction
- ColBERT
- Prompt Construction
- Context Injection
- Citation
- Source Attribution
- Lost in the Middle
- Long Context
- MRR
- NDCG
- Hit Rate
- Faithfulness
- Groundedness
- Answer Relevancy
- Indexing Pipeline
- Ingestion Pipeline
- Embedding Cache
- Query Cache
- Incremental Updates
- Parent Document Retrieval
- Multi Vector Retrieval
- Self Query Retrieval
- Graph RAG
- Agentic RAG
- RAPTOR
- Contextual Retrieval

Этот раздел является только планом будущих синхронизаций. Перечисленные concept-заметки пока не создаются.
