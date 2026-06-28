---
type: concept
area: Algorithms & Data Structures
status: draft
created: 2026-06-27
updated: 2026-06-29
tags:
  - algorithms
  - recursion
  - trees
confidence: 0
---

# Tree Traversal

## Простое объяснение

Tree Traversal — обход всех узлов дерева в определенном порядке.

## Зачем это нужно

Обходы деревьев нужны для файловых систем, AST, DOM, деревьев решений и задач на бинарные деревья.

## Как это работает

Рекурсивный обход обычно обрабатывает текущий узел и затем рекурсивно обходит дочерние узлы.

Если обход должен вернуть вычисленный результат, нужно использовать возвращаемые значения из поддеревьев.

## Пример

```python
def dfs(node):
    if node is None:
        return
    dfs(node.left)
    dfs(node.right)
```

## Типичные ошибки

- Забывать Base Case для пустого узла.
- Путать порядок обхода и момент обработки текущего узла.

## Связанные темы

- [[Algorithms/Tree|Tree]] · [[Algorithms/DFS|DFS]] · [[Algorithms/Recursion/Trees/DFS на дереве|DFS на дереве]] · [[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Recursion/Trees/Binary Tree Traversal|Binary Tree Traversal]]
