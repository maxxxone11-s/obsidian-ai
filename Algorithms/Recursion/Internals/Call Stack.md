---
type: concept
area: Algorithms & Data Structures
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - algorithms
  - recursion
  - stack
confidence: 96
difficulty: medium
---

# Call Stack и размотка рекурсии

## Простое объяснение
Call Stack — это стек вызовов функций. Каждый рекурсивный вызов создает отдельный stack frame со своими аргументами, локальными переменными и местом, куда нужно вернуться после завершения следующего вызова.

Сначала рекурсия погружается всё глубже, а после [[Algorithms/Recursion/Basics/Base Case|Base Case]] начинает разматываться обратно.

## Зачем это нужно
Без понимания Call Stack трудно понять [[Algorithms/DFS|DFS]], обходы деревьев, backtracking и большинство рекурсивных алгоритмов.

Call Stack объясняет, почему `print` до рекурсивного вызова работает в прямом порядке, а `print` после вызова — в обратном.

## Как это работает
Каждый вызов ждет результата следующего вызова. Пока самый глубокий вызов не вернул значение, предыдущие вызовы не могут продолжить выполнение.

```python
def countdown(n: int) -> None:
    if n == 0:
        print("start")
        return
    countdown(n - 1)
    print(n)


countdown(3)
```

Вывод будет `start`, `1`, `2`, `3`, потому что `print(n)` выполняется уже во время размотки.

## Пример
```python
def factorial(n: int) -> int:
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

Для `factorial(3)` стек сначала строится так: `factorial(3)` → `factorial(2)` → `factorial(1)` → `factorial(0)`. Затем ответы идут назад: `1`, `1`, `2`, `6`.

## Типичные ошибки
- Путать вызов и возврат.
- Думать, что все вызовы используют одну и ту же переменную `n`.
- Не понимать, почему `RecursionError` связан с переполнением глубины стека.

## Связанные темы
[[Algorithms/Recursion/Basics/Base Case|Base Case]] · [[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Stack|Stack]] · [[Algorithms/DFS|DFS]]

