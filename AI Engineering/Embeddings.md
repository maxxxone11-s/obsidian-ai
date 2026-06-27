---
type: concept
area: llm-engineering
status: draft
created: 2026-06-26
updated: 2026-06-27
tags: [embeddings, vectors, representation]
confidence: 0
---

# Embeddings

Преобразование текста в векторное представление.

## Простое объяснение

Embeddings — это вектора чисел, которые представляют смысл текста.

## Интуитивное объяснение

Как превращение слов в точки в многомерном пространстве — похожие слова близко друг к другу.

## Зачем это нужно

- Поиск похожего контента
- Кластеризация текстов
- Основа для RAG систем

## Как это работает

### Механизм
- Модель embedding преобразует текст в вектор
- Векторы одинакового размера (например, 1536)
- Похожесть = близость в пространстве

## Пример

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer('all-MiniLM-L6-v2')
embedding = model.encode("Hello world")
print(embedding.shape)  # (384,)
```

## Типичные ошибки

- Использование неправильной модели для данных
- Не нормализация embeddings
- Путаница с distance metric

## Связанные темы

- [[RAG]] — использует embeddings
- [[Vector Database]] — хранит embeddings
- [[LLM]] — генерирует текст
- [[AI Agent]] — может использовать embeddings
