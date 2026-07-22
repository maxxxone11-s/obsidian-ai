---
type: concept
area: Vector Databases
status: learned
created: 2026-07-17
updated: 2026-07-17
aliases:
  - Search Candidate List
tags:
  - vector-databases
---

# Параметр efSearch

Область: [[Vector Databases/Vector Databases|Vector Databases]]

## Академическое определение

`efSearch` определяет размер списка кандидатов, исследуемых алгоритмом во время выполнения одного поискового запроса по HNSW.

## Инженерное назначение

Параметр позволяет управлять компромиссом между latency и Recall без перестройки индекса.

## Причина существования

Один индекс может обслуживать сценарии с разными требованиями к скорости и качеству, поэтому глубину online-поиска необходимо настраивать отдельно от структуры графа.

## Простое объяснение

`efSearch` определяет, насколько тщательно алгоритм исследует уже построенный граф.

## Как это работает

- Во время запроса поддерживается список до `efSearch` перспективных кандидатов.
- Алгоритм исследует кандидатов и их соседей.
- Увеличение списка повышает вероятность найти действительно ближайший embedding.
- Параметр применяется при каждом пользовательском запросе и не меняет структуру индекса.

## Пример

При `efSearch = 20` поиск обычно быстрее, но исследует меньше кандидатов. При `efSearch = 300` latency возрастает, зато Recall обычно становится выше.

## Типичные ошибки

- Путать `efSearch` с `efConstruction`.
- Считать, что изменение `efSearch` требует перестройки индекса.
- Считать, что `efSearch` меняет структуру графа.

## Связанные темы

[[Vector Databases/HNSW|HNSW]] · [[Vector Databases/Параметр efConstruction|efConstruction]] · [[Vector Databases/Параметр M в HNSW|M]] · [[Vector Databases/Recall в Approximate Nearest Neighbor|ANN Recall]]

## Вопросы для проверки

- Чем `efSearch` отличается от `efConstruction`?
- Почему `efSearch` обычно меняют первым в production?
- Почему увеличение `efSearch` повышает Recall?

## Следующие темы

[[Vector Databases/Greedy Search в HNSW|Greedy Search]] · [[Multi Candidate Search]]
