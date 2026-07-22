---
type: concept
area: Vector Databases
status: learned
created: 2026-07-13
updated: 2026-07-17
aliases:
  - HNSW как граф поиска
  - Navigable Small World Graph
  - NSW Graph
tags:
  - vector-databases
---

# HNSW

Область: [[Vector Databases/Vector Databases|Vector Databases]]

## Академическое определение

HNSW хранит embeddings в виде многоуровневого графа, где каждый узел соединён с ограниченным количеством ближайших соседей. Поиск выполняется навигацией по связям графа вместо сравнения запроса со всеми объектами базы.

## Инженерное назначение

HNSW используется как ANN-индекс, который резко сокращает количество вычислений при поиске ближайших embeddings и позволяет масштабировать vector search.

## Причина существования

Полный перебор требует вычислять similarity для каждого embedding. Граф позволяет двигаться только через перспективные области пространства, сохраняя высокое качество поиска.

## Простое объяснение

Каждый embedding знает несколько ближайших соседей. Алгоритм начинает с одной вершины и переходит к тем соседям, которые становятся всё ближе к запросу.

## Как это работает

1. Выбирается стартовый узел.
2. Вычисляется его similarity с запросом.
3. Рассматриваются связанные с ним соседи.
4. Несколько перспективных кандидатов сохраняются для дальнейшего исследования.
5. Навигация продолжается в направлении ближайших embeddings.
6. Иерархические уровни сначала обеспечивают грубые переходы, затем уточняют поиск на Level 0.

## Пример

Упрощённый путь может выглядеть так: `Transformer → FastAPI → REST API → ASGI`. Каждый следующий узел увеличивает similarity с запросом. Реальный HNSW исследует несколько кандидатов одновременно, а не единственный маршрут.

## Типичные ошибки

- Считать, что HNSW проверяет все embeddings.
- Представлять поиск как движение только по одному пути.
- Считать граф полным, где каждый embedding связан со всеми остальными.
- Думать, что HNSW всегда гарантирует тот же Top-K, что и Exact Search.

## Связанные темы

[[Vector Databases/Approximate Nearest Neighbor (ANN)|ANN]] · [[Vector Databases/Greedy Search в HNSW|Greedy Search]] · [[Vector Databases/Local Maximum в HNSW|Local Maximum]] · [[Vector Databases/Hierarchical Levels в HNSW|Hierarchical Levels]] · [[Vector Databases/Параметр M в HNSW|M]] · [[Vector Databases/Параметр efConstruction|efConstruction]] · [[Vector Databases/Параметр efSearch|efSearch]] · [[AI Engineering/Vector Database|Vector Database]]

## Вопросы для проверки

- Почему графовая навигация быстрее полного перебора?
- Почему каждый embedding хранит ограниченное число соседей?
- Почему HNSW исследует несколько кандидатов?

## Следующие темы

[[Vector Databases/Hierarchical Levels в HNSW|Hierarchical Levels]] · [[Vector Databases/Параметр M в HNSW|M]] · [[Vector Databases/Параметр efConstruction|efConstruction]] · [[Vector Databases/Параметр efSearch|efSearch]] · [[Vector Databases/Жизненный цикл параметров HNSW|Жизненный цикл параметров HNSW]]
