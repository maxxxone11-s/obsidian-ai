---
type: concept
area: Vector Databases
status: learned
created: 2026-07-13
updated: 2026-07-13
aliases:
  - Brute Force Vector Search
  - Linear Vector Search
  - Exhaustive Search
tags:
  - vector-databases
---

# Exact Search

## Академическое определение

Exact Search — алгоритм поиска ближайших соседей, при котором embedding запроса сравнивается с каждым embedding в базе. После вычисления similarity для всех объектов результаты сортируются, и система возвращает наиболее похожие элементы.

## Инженерное назначение

Exact Search обеспечивает максимально точный результат и служит эталоном для оценки качества приближённых алгоритмов поиска.

## Причина существования

Метод гарантирует нахождение действительно ближайших соседей без приближений. Без него было бы сложнее измерить, какую часть правильных результатов теряет ANN-индекс.

## Простое объяснение

Система проверяет каждый embedding, вычисляет similarity, сортирует результаты и возвращает Top-K.

## Как это работает

1. Получить embedding запроса.
2. Вычислить similarity со всеми embeddings базы.
3. Отсортировать результаты.
4. Вернуть Top-K наиболее похожих объектов.

Сложность поиска — `O(N)`, где `N` — количество embeddings в базе.

## Пример

Если база содержит 10 000 000 embeddings, Exact Search выполнит примерно 10 000 000 вычислений similarity независимо от того, где находится правильный ответ.

## Типичные ошибки

- Считать, что Exact Search использует ANN-индекс.
- Думать, что полный перебор хорошо масштабируется на очень большие базы.
- Не учитывать линейный рост времени поиска вместе с количеством embeddings.

## Связанные темы

[[Vector Databases/Approximate Nearest Neighbor (ANN)|Approximate Nearest Neighbor]] · [[Vector Databases/HNSW|HNSW]] · [[Vector Databases/Recall в Approximate Nearest Neighbor|ANN Recall]] · [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]] · [[RAG/Top-K Retrieval|Top-K Retrieval]]

## Вопросы для проверки

- Почему Exact Search всегда находит действительно ближайшие результаты?
- Почему сложность поиска равна `O(N)`?
- Почему Exact Search становится непрактичным на больших объёмах данных?

## Следующие темы

[[Vector Databases/Approximate Nearest Neighbor (ANN)|Approximate Nearest Neighbor]] · [[Vector Databases/HNSW|HNSW]]
