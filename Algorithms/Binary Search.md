---
type: concept
area: Algorithms & Data Structures
status: draft
created: 2026-06-26
updated: 2026-06-26
tags:
  - algorithms
confidence: 0
---

# Binary Search

## Простое объяснение
Binary Search ищет ответ, каждый раз отбрасывая половину вариантов.

## Зачем это нужно
Используется для поиска в sorted arrays и задач “binary search on answer”.

## Как это работает
Поддерживаются границы left/right, выбирается mid, затем одна половина пространства поиска отбрасывается.

## Пример
Найти позицию target в отсортированном массиве.

## Типичные ошибки
- Ошибаться в границах left/right и получать infinite loop.

## Связанные темы
[[Two Pointers]] · [[Dynamic Programming]]
