---
type: module_plan
area: RAG
status: learning
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

status: learning

Коротко: понять ограничения знаний LLM, причины hallucinations и место RAG среди способов адаптации модели.

Related concepts:

- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Transformers/Разделение ролей LLM и RAG|Разделение ролей LLM и RAG]]
- [[LLM Engineering/Context Window|Context Window]]
- [[LLM Engineering/Production Pipeline LLM-приложения|Production Pipeline LLM-приложения]]

Topics:

- [[AI Engineering/RAG|Retrieval-Augmented Generation (RAG)]] — learned
- Почему LLM забывают знания
- Контекстное окно
- Hallucinations
- Fine-tuning vs RAG
- Когда нужен RAG, а когда нет
- Архитектура RAG целиком

### 2. Embeddings

status: learning

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

- [[AI Engineering/Embeddings|Embedding]] — learned
- Почему embedding — это не просто вектор — learned
- Семантическое пространство
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]] — learned
- Euclidean Distance
- Dot Product
- Почему похожие предложения оказываются рядом
- Размерность embedding
- Как создаются embeddings

### 3. Chunking

status: learning

Коротко: научиться делить документы на поисковые единицы с учётом структуры, смысла и ограничений retrieval.

Prerequisites:

- Embeddings

Related concepts:

- [[LLM Engineering/Context Window|Context Window]]
- [[LLM Engineering/Token Counting|Token Counting]]

Topics:

- [[RAG/Chunk|Chunk]] — learned
- Почему нельзя хранить документ целиком — learned
- Chunk Size
- [[RAG/Fixed-size Chunking|Fixed-size Chunking]] — learned
- [[RAG/Chunk Overlap|Chunk Overlap]] — learned
- Sliding Window
- [[RAG/Recursive Chunking|Recursive Chunking]] — learned
- [[RAG/Semantic Chunking]] — learned
- Markdown Chunking
- Code Chunking
- Таблицы
- PDF
- Реальные ошибки chunking

### 4. Vector Database

status: learning

Коротко: изучить минимально необходимую для RAG часть хранения embeddings и приближённого поиска ближайших соседей.

Prerequisites:

- Embeddings
- Chunking

Related concepts:

- [[Python Backend/PostgreSQL|PostgreSQL]]
- [[Python Backend/SQL|SQL]]

Topics:

- [[AI Engineering/Vector Database|Vector Database]] — learning
- Почему обычного SQL недостаточно для векторного поиска
- ANN Search
- HNSW
- IVF
- pgvector
- Qdrant
- Pinecone

### 5. Retrieval

status: learning

Коротко: научиться извлекать релевантные документы и управлять полнотой, точностью и ограничениями выдачи.

Prerequisites:

- Embeddings
- Vector Database

Related concepts:

- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- [[Machine Learning/Accuracy Precision Recall и F1|Accuracy Precision Recall и F1]]

Topics:

- [[RAG/Retrieval|Retrieval]] — learned
- Similarity Search
- [[RAG/Top-K Retrieval|Top-K Retrieval]] — learned
- Threshold
- Metadata Filtering
- Dense Retrieval
- Sparse Retrieval
- BM25
- Query Expansion
- Multi Query Retrieval

### 6. Hybrid Search

status: learning

Коротко: объединить семантический и лексический поиск, когда одного embedding-поиска недостаточно.

Prerequisites:

- Retrieval

Topics:

- Dense Search
- Sparse Search
- BM25
- [[RAG/Hybrid Search|Hybrid Search]] — learned
- [[RAG/Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion (RRF)]] — learned
- Когда использовать каждый подход

### 7. Reranking

status: learning

Коротко: научиться повторно ранжировать найденные документы более точной моделью перед передачей контекста LLM.

Prerequisites:

- Retrieval
- Hybrid Search

Related concepts:

- [[Transformers/Index|Transformers]]

Topics:

- Cross Encoder
- Bi Encoder
- [[RAG/Reranking|Reranking]] — learned
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

status: learned

Коротко: измерять качество retrieval и ответа, отделяя нахождение документов от генерации по найденному контексту.

Prerequisites:

- Retrieval
- Generation

Related concepts:

- [[Machine Learning/Accuracy Precision Recall и F1|Accuracy Precision Recall и F1]]

Topics:

- [[RAG/Evaluation|Evaluation]] — learned
- [[RAG/Ground Truth|Ground Truth]] — learned
- [[Machine Learning/Accuracy Precision Recall и F1|Recall]] — learned
- [[Machine Learning/Accuracy Precision Recall и F1|Precision]] — learned
- [[RAG/Mean Reciprocal Rank (MRR)|Mean Reciprocal Rank (MRR)]] — learned
- [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]] — learned
- [[RAG/Hit Rate|Hit Rate]] — learned
- [[RAG/Faithfulness|Faithfulness]] — learned
- [[RAG/Faithfulness|Groundedness]] — learned
- [[RAG/Answer Relevancy|Answer Relevancy]] — learned
- [[RAG/Context Precision|Context Precision]] — learned
- [[RAG/Context Recall|Context Recall]] — learned
- [[RAG/LLM-as-a-Judge|LLM-as-a-Judge]] — learned

### 10. Production RAG

status: learning

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

- [[RAG/Document Loader|Document Loader]] — learned
- [[RAG/Indexing Pipeline|Indexing Pipeline]] — learned
- [[RAG/Query Pipeline|Query Pipeline]] — learned
- [[RAG/Orchestrator|Orchestrator]] — learned
- [[RAG/Query Transformation|Query Transformation]] — learned
- [[RAG/Production RAG Pipeline|Production RAG Pipeline]] — learning
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
