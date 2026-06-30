---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - python
  - ml-engineering
confidence: 0.99
difficulty: easy
---

# Tuple Unpacking

## Простое объяснение

Функция может вернуть несколько значений кортежем, а Python сразу распределит их по переменным.

## Зачем это нужно

Tuple unpacking часто используется в PyTorch и Python-проектах, например при возврате loss и batch size из helper-функции.

## Как это работает

```text
return loss, batch_size
↓
loss_value, batch_size = loss_batch(...)
```

## Пример

```python
a, b = function()
```

## Типичные ошибки

- Не понимать, что функция возвращает несколько объектов.
- Ожидать одно значение там, где возвращается кортеж.

## Вопросы для проверки

- Что такое tuple unpacking?
- Почему можно сразу присвоить две переменные?

## Следующие темы

- Advanced Python Functions

## Связанные темы

- [[train_utils.py]] · [[loss.item()]] · [[Weighted Average Loss]]
