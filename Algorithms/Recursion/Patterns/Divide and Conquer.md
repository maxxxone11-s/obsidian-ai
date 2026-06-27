---
type: concept
area: Algorithms & Data Structures
status: draft
created: 2026-06-27
updated: 2026-06-27
tags:
  - algorithms
  - recursion
confidence: 0
---

# Divide and Conquer

## Простое объяснение
Divide and Conquer — подход, где задача делится на несколько меньших подзадач, каждая решается отдельно, а затем результаты объединяются.

## Зачем это нужно
Этот подход лежит в основе merge sort, quick sort, бинарного поиска и многих рекурсивных алгоритмов.

## Как это работает
Алгоритм выполняет три шага: разделить задачу, решить части, объединить ответы.

## Пример
В merge sort массив делится пополам, половины сортируются рекурсивно, затем сливаются.

## Типичные ошибки
- Путать обычную рекурсию с divide and conquer: не каждая рекурсия делит задачу на несколько частей.

## Связанные темы
[[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Binary Search|Binary Search]] · [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]]

