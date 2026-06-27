---
type: concept
area: Algorithms & Data Structures
status: draft
created: 2026-06-26
updated: 2026-06-27
tags:
  - algorithms
confidence: 0
---

# Hash Table

## Простое объяснение

Hash Table хранит пары key-value и даёт быстрый доступ по ключу.

## Зачем это нужно

Это основа словарей, множеств, frequency map и многих LeetCode-задач.

## Как это работает

Ключ превращается в hash, по которому выбирается bucket для хранения значения.

## Пример

Посчитать частоту чисел в массиве через dictionary.

## Типичные ошибки

- Забывать про collisions и думать, что hash table всегда строго O(1).

## Связанные темы

- [[Two Pointers]]
