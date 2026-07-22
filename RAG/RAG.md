---
type: area_index
area: RAG
aliases:
  - RAG
tags:
  - rag
  - area-index
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
- [[RAG/Semantic Chunking]]
- [[RAG/Retrieval|Retrieval]]
- [[RAG/Top-K Retrieval|Top-K Retrieval]]
- [[RAG/Reranking|Reranking]]
- [[RAG/Hybrid Search|Hybrid Search]]
- [[RAG/Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion (RRF)]]
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
- [[RAG/Document Loader|Document Loader]]
- [[RAG/Indexing Pipeline|Indexing Pipeline]]
- [[RAG/Query Pipeline|Query Pipeline]]
- [[RAG/Orchestrator|Orchestrator]]
- [[RAG/Query Transformation|Query Transformation]]
- [[RAG/Query Rewrite|Query Rewrite]]
- [[RAG/Query Expansion|Query Expansion]]
- [[RAG/HyDE|HyDE]]
- [[RAG/Multi Query Retrieval|Multi Query Retrieval]]
- [[RAG/Step-back Prompting|Step-back Prompting]]
- [[RAG/Prompt Construction|Prompt Construction]]
- [[RAG/Context Construction|Context Construction]]
- [[RAG/Lost in the Middle|Lost in the Middle]]
- [[RAG/Ingestion Pipeline|Ingestion Pipeline]]
- [[RAG/Production RAG Pipeline|Production RAG Pipeline]]
- [[RAG/SearchResult|SearchResult]]

## Концепции в процессе изучения

- [[AI Engineering/Vector Database|Vector Database]]

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
- Структурные стратегии и [[RAG/Semantic Chunking]]
- Markdown, code, tables и PDF

### Vector Database

- ANN Search
- HNSW и IVF
- pgvector, Qdrant и Pinecone

### Retrieval

- Dense и Sparse Retrieval
- BM25
- [[RAG/Query Expansion|Query Expansion]] и [[RAG/Multi Query Retrieval|Multi Query Retrieval]]

### Hybrid Search

- Dense Search + Sparse Search
- [[RAG/Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion]]

### Reranking

- Cross Encoder и Bi Encoder
- ColBERT и Late Interaction
- Top-K → Rerank → Top-N

### Generation

- [[RAG/Prompt Construction|Prompt Construction]]
- [[RAG/Context Construction|Context Construction]]
- Context Injection
- Citation и Source Attribution
- Context Compression, Long Context и [[RAG/Lost in the Middle|Lost in the Middle]]

### Evaluation

- Retrieval metrics
- Faithfulness, Groundedness и Answer Relevancy

### Production RAG

- [[RAG/Document Loader|Document Loader]] и [[RAG/Indexing Pipeline|Indexing Pipeline]]
- [[RAG/Ingestion Pipeline|Ingestion Pipeline]] и [[RAG/SearchResult|SearchResult]]
- [[RAG/Query Pipeline|Query Pipeline]], [[RAG/Orchestrator|Orchestrator]] и [[RAG/Query Transformation|Query Transformation]]
- [[RAG/Query Rewrite|Query Rewrite]], [[RAG/Query Expansion|Query Expansion]], [[RAG/HyDE|HyDE]], [[RAG/Multi Query Retrieval|Multi Query Retrieval]] и [[RAG/Step-back Prompting|Step-back Prompting]]
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

- [[LLM Engineering/LLM Engineering|LLM Engineering]]
- [[Transformers/Transformers|Transformers]]
- [[Machine Learning/Machine Learning|Machine Learning]]
- [[Python Backend/Python Backend|Python Backend]]
- [[AI Agents/AI Agents|AI Agents]]

Concept-заметки будут создаваться позднее из KNOWLEDGE_EXPORT. Плановые темы не являются stub-файлами.
