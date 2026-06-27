---
type: concept
area: Algorithms & Data Structures
status: draft
created: 2026-06-27
updated: 2026-06-27
tags:
  - algorithms
  - recursion
  - trees
confidence: 0
---

# Binary Tree Traversal

## Простое объяснение

Binary Tree Traversal — обход бинарного дерева, где у каждого узла может быть левый и правый ребенок.

## Зачем это нужно

Это база для задач на глубину дерева, поиск пути, проверку симметрии, inorder/preorder/postorder обходы.

## Как это работает

Рекурсивная функция получает узел. Если узла нет, возвращает базовое значение. Если узел есть, обрабатывает его и вызывает себя для левого и правого поддерева.

## Пример

```python
def inorder(node):
    if node is None:
        return []
    return inorder(node.left) + [node.value] + inorder(node.right)
```

## Типичные ошибки

- Забывать `node is None`.
- Путать preorder, inorder и postorder.
- Не возвращать результат рекурсивных вызовов.

## Связанные темы

- [[Algorithms/Recursion/Trees/Tree Traversal|Tree Traversal]] · [[Algorithms/DFS|DFS]] · [[Algorithms/Recursion/Basics/Base Case|Base Case]]
