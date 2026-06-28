---
type: concept
area: Algorithms & Data Structures
status: draft
created: 2026-06-26
updated: 2026-06-29
tags:
  - algorithms
confidence: 0
---

# DFS

## Простое объяснение

DFS — обход графа или дерева в глубину.

На дереве DFS особенно естественно реализуется рекурсией: функция обрабатывает текущий узел и вызывает себя для каждого ребенка.

## Зачем это нужно

Используется для поиска связности, путей, циклов, компонентов и backtracking-задач.

## Как это работает

Алгоритм идёт как можно глубже по одному пути, затем возвращается назад. Реализуется рекурсией или stack.

## Пример

Обойти все вершины компоненты графа через рекурсивный dfs(node).

## Типичные ошибки

- Забывать отмечать visited и попадать в бесконечный цикл.

## Связанные темы

- [[Graphs]] · [[Stack]] · [[Tree]] · [[Algorithms/Recursion/Trees/DFS на дереве|DFS на дереве]] · [[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Recursion/Internals/Call Stack|Call Stack]]
