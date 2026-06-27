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

# Recursive Thinking

## Простое объяснение

Recursive Thinking — это привычка видеть задачу как меньшую задачу того же типа плюс небольшое действие.

## Зачем это нужно

Так легче строить рекурсивные решения для строк, деревьев, DFS, backtracking и divide and conquer.

## Как это работает

Нужно ответить на три вопроса: какая самая маленькая задача, как уменьшить текущую задачу и как использовать ответ меньшей задачи.

## Пример

Для суммы: `sum(n) = n + sum(n - 1)`.

## Типичные ошибки

- Думать о всей цепочке вызовов сразу вместо формулы одного шага.

## Связанные темы

- [[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Recursion/Basics/Base Case|Base Case]] · [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]]
