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

# Base Case

## Простое объяснение

Base Case — это условие, при котором рекурсия прекращается. Это самая маленькая версия задачи, где ответ уже известен сразу.

Например, сумма чисел до `0` равна `0`, а `0!` равен `1`.

## Зачем это нужно

Без Base Case рекурсия никогда не остановится: функция будет продолжать вызывать себя, пока Python не выбросит `RecursionError`.

Base Case нужен не только для остановки. Он запускает обратный процесс: после него стек вызовов начинает разматываться, а значения возвращаются вверх.

## Как это работает

Рекурсивная функция сначала проверяет, не дошла ли задача до минимального состояния. Если дошла — возвращает готовый ответ. Если нет — уменьшает задачу и вызывает себя снова.

```python
def factorial(n: int) -> int:
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

`factorial(0)` — это дно рекурсии. После него каждый предыдущий вызов может продолжить работу.

## Пример

```python
def reverse(s: str) -> str:
    if len(s) <= 1:
        return s
    return reverse(s[1:]) + s[0]
```

Для строки важно использовать `len(s) <= 1`, потому что пустая строка тоже является корректным базовым случаем.

## Типичные ошибки

- Не добавить Base Case вообще.
- Сделать Base Case слишком узким, например `len(s) == 1` и забыть про пустую строку.
- Возвращать неправильное нейтральное значение: для суммы нужен `0`, для факториала — `1`.

## Связанные темы

- [[Algorithms/Recursion/Basics/Recursion|Recursion]] · [[Algorithms/Recursion/Internals/Call Stack|Call Stack]] · [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]]
