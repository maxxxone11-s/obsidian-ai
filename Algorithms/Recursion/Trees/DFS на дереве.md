---
type: concept
area: Algorithms & Data Structures
status: learned
created: 2026-06-29
updated: 2026-06-29
tags:
  - algorithms
  - recursion
  - trees
  - dfs
confidence: 0.96
difficulty: medium
---

# DFS на дереве

## Кратко

DFS выполняет обход дерева, проходя максимально глубоко по каждой ветке, прежде чем перейти к следующей.

## Простое объяснение

Если встретил ребенка, выполни для него тот же самый алгоритм. Когда дети закончились, вернись назад.

## Зачем это нужно

DFS используется практически во всех алгоритмах работы с деревьями, файловыми системами, AST, графами, Git, компиляторами и AI.

## Как это работает

Каждый узел обрабатывается один раз. Затем рекурсивно вызывается обход для каждого ребенка. После завершения обхода ребенка выполнение продолжается у родителя.

Функция знает только текущий узел и его детей, а не всё дерево целиком.

## Пример

```python
def dfs(node):
    print(node.value)
    for child in node.children:
        dfs(child)
```

## Типичные ошибки

- Воспринимать обход как маршрут с возвратами, а не как обработку узлов.
- Запускать DFS не с корня дерева.
- Считать, что алгоритм знает всё дерево целиком.

## Вопросы для проверки

- Почему DFS естественно реализуется рекурсией?
- Почему функция знает только текущий узел?
- Чем отличается маршрут обхода от порядка вывода?

## Следующие темы

- [[Algorithms/DFS|DFS на графах]]
- [[Algorithms/Recursion/Trees/Binary Tree Traversal|Binary Tree Traversal]]
- Backtracking

## Связанные темы

- [[Algorithms/Recursion/Basics/Recursion|Recursion]]
- [[Algorithms/Recursion/Internals/Call Stack|Call Stack]]
- [[Algorithms/Tree|Tree]]
- [[Algorithms/Graphs|Graph]]
- [[Algorithms/DFS|Depth First Search]]
- [[Algorithms/Recursion/Trees/Tree Traversal|Tree Traversal]]
