---
type: index
area: RAG
created: 2026-06-26
updated: 2026-07-11
tags:
  - index
  - system
  - rag
---

# RAG

Retrieval-Augmented Generation: поиск релевантных внешних данных и передача их LLM как контекста для генерации ответа.

## План модуля

- [[RAG/Plan|RAG Plan]]

## Изученные концепции

- [[AI Engineering/RAG|Retrieval-Augmented Generation (RAG)]]
- [[AI Engineering/Embeddings|Embedding]]
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- [[RAG/Chunk|Chunk]]
- [[RAG/Fixed-size Chunking|Fixed-size Chunking]]
- [[RAG/Chunk Overlap|Chunk Overlap]]
- [[RAG/Recursive Chunking|Recursive Chunking]]
- [[Semantic Chunking]]
- [[RAG/Retrieval|Retrieval]]
- [[RAG/Top-K Retrieval|Top-K Retrieval]]
- [[RAG/Reranking|Reranking]]
- [[RAG/Hybrid Search|Hybrid Search]]
- [[Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion (RRF)]]
- [[RAG/Evaluation|Evaluation]]
- [[RAG/Ground Truth|Ground Truth]]
- [[RAG/Mean Reciprocal Rank (MRR)|Mean Reciprocal Rank (MRR)]]
- [[RAG/Hit Rate|Hit Rate]]
- [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]]
- [[RAG/Faithfulness|Faithfulness]]
- [[RAG/Answer Relevancy|Answer Relevancy]]
- [[RAG/Context Precision|Context Precision]]
- [[RAG/Context Recall|Context Recall]]
- [[RAG/LLM-as-a-Judge|LLM-as-a-Judge]]

## Концепции в процессе изучения

- [[AI Engineering/Vector Database|Vector Database]]
- [[RAG/Document Loader|Document Loader]]
- [[RAG/Indexing Pipeline|Indexing Pipeline]]
- [[RAG/Query Pipeline|Query Pipeline]]
- [[RAG/Production RAG Pipeline|Production RAG Pipeline]]

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

## Основные блоки

### Основы RAG

- Проблема актуальности знаний LLM
- Hallucinations
- Fine-tuning vs RAG
- Архитектура RAG

### Embeddings

- Семантическое пространство
- Метрики сходства
- Создание embeddings
- Поиск похожих документов

### Chunking

- Размер и overlap chunks
- Структурные стратегии и [[Semantic Chunking]]
- Markdown, code, tables и PDF

### Vector Database

- ANN Search
- HNSW и IVF
- pgvector, Qdrant и Pinecone

### Retrieval

- Dense и Sparse Retrieval
- BM25
- Query Expansion и Multi Query Retrieval

### Hybrid Search

- Dense Search + Sparse Search
- [[Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion]]

### Reranking

- Cross Encoder и Bi Encoder
- ColBERT и Late Interaction
- Top-K → Rerank → Top-N

### Generation

- Prompt Construction
- Context Injection
- Citation и Source Attribution
- Context Compression и Long Context

### Evaluation

- Retrieval metrics
- Faithfulness, Groundedness и Answer Relevancy

### Production RAG

- Indexing и Ingestion Pipelines
- Cache, versioning и incremental updates
- Monitoring и Cost Optimization

### Advanced RAG

- Parent Document и Multi Vector Retrieval
- Self Query, Graph RAG и Agentic RAG
- RAPTOR и Contextual Retrieval

## Практика

- Создание embeddings и similarity search.
- Эксперименты с chunking.
- Реализация retrieval, hybrid search и reranking.
- Evaluation retrieval и generation.
- Production-подобный финальный RAG-проект.

## Связанные области

- [[LLM Engineering/Index|LLM Engineering]]
- [[Transformers/Index|Transformers]]
- [[Machine Learning/Index|Machine Learning]]
- [[Python Backend/Index|Python Backend]]
- [[AI Agents/Index|AI Agents]]

Concept-заметки будут создаваться позднее из KNOWLEDGE_EXPORT. Плановые темы не являются stub-файлами.
