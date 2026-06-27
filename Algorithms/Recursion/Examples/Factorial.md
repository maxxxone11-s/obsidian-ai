---
type: concept
area: Algorithms & Data Structures
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - algorithms
  - recursion
confidence: 100
difficulty: easy
---

# Рекурсивный факториал

## Простое объяснение

Факториал естественно выражается через меньший факториал: `5! = 5 * 4!`.

Каждый вызов знает только одно правило: взять текущий `n` и умножить на результат `factorial(n - 1)`.

## Зачем это нужно

Факториал — классический пример рекурсивного мышления. Он показывает, как большая задача сводится к почти такой же, но меньшей.

## Как это работает

Формула:

- `factorial(n) = n * factorial(n - 1)`;
- `factorial(0) = 1`.

`factorial(0)` нужен как базовый случай и нейтральный элемент умножения.

## Пример

```python
def factorial(n: int) -> int:
    if n == 0:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # 120
```

## Типичные ошибки

- Реализовывать факториал через `global result`.
- Забывать вернуть значение из рекурсивного вызова.
- Не понимать, почему `factorial(0)` возвращает `1`.

## Связанные темы

- [[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Recursion/Basics/Base Case|Base Case]] · [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]]
