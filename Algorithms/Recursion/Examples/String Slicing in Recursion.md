---
type: concept
area: Algorithms & Data Structures
status: needs_review
created: 2026-06-27
updated: 2026-06-27
tags:
  - algorithms
  - recursion
  - strings
confidence: 0
---

# String Slicing in Recursion

## Простое объяснение

String Slicing in Recursion — использование срезов строки, чтобы передавать в следующий рекурсивный вызов меньшую строку.

## Зачем это нужно

Срезы часто встречаются в задачах на разворот строки, палиндромы, парсинг и обработку подстрок.

## Как это работает

`s[1:]` убирает первый символ, а `s[1:-1]` убирает первый и последний символ. Эти операции уменьшают задачу.

## Пример

```python
def is_palindrome(s: str) -> bool:
    if len(s) <= 1:
        return True
    return s[0] == s[-1] and is_palindrome(s[1:-1])
```

## Типичные ошибки

- Писать `s[1:-2]`, когда нужно убрать только первый и последний символ.
- Забывать, что верхняя граница среза не включается.
- Не учитывать пустую строку.

## Связанные темы

- [[Algorithms/Recursion/Examples/Рекурсивный разворот строки|Рекурсивный разворот строки]] · [[Algorithms/Recursion/Examples/Рекурсивная проверка палиндрома|Рекурсивная проверка палиндрома]] · [[Algorithms/Recursion/Basics/Base Case|Base Case]]
