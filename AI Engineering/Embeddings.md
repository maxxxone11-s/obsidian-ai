---
type: concept
area: RAG
status: learned
created: 2026-06-26
updated: 2026-07-11
tags: [rag, embeddings, vectors, semantic-search]
aliases: [Embedding, Text Embedding, Semantic Embedding]
confidence: high
difficulty: beginner
---

# Embedding

## Академическое определение

Embedding — обученное числовое представление объекта, в котором геометрические отношения между векторами отражают полезные семантические отношения между объектами.

## Инженерное назначение

Embedding заменяет прямое сравнение текста сравнением числовых представлений и тем самым делает возможным семантический поиск, кластеризацию и retrieval.

## Причина существования

Обычное сравнение строк учитывает символы и слова, но плохо отражает смысл. Embedding-модель переводит поиск в математическую задачу сравнения векторов.

## Простое объяснение

Модель превращает текст, изображение или другой объект в точку многомерного пространства. Похожие по смыслу объекты оказываются рядом, даже если используют разные слова.

## Как это работает

1. Объект передаётся отдельной embedding-модели.
2. Модель возвращает вектор фиксированной размерности.
3. Вектор сохраняется вместе с исходным объектом и metadata.
4. Вектор запроса сравнивается с векторами документов.
5. Наиболее близкие объекты возвращаются retriever.

## Пример

Запрос «Как приготовить настоящую пасту?» и документ «Классический рецепт Carbonara» могут иметь близкие embeddings без совпадения основных слов.

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("all-MiniLM-L6-v2")
embedding = model.encode("Как приготовить пасту?")
print(embedding.shape)
```

## Типичные ошибки

- Считать embedding любым набором чисел.
- Путать отдельную embedding-модель с внутренним Embedding Layer Transformer.
- Думать, что embeddings существуют только для слов.
- Использовать метрику, не соответствующую модели и способу индексации.

## Связанные темы

[[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]] · [[Retrieval]] · [[Embedding Model]] · [[Transformers/Embedding Layer|Embedding Layer]]

## Вопросы для проверки

- Почему embedding — не просто произвольный набор чисел?
- Какие объекты можно представить embedding?
- Чем embedding-модель отличается от Embedding Layer внутри LLM?

## Следующие темы

[[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]] · [[Vector Database]]
