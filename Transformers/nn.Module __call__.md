---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-03
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - nn.Module.__call__
---

# nn.Module __call__

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

`nn.Module.__call__()` — механизм PyTorch, который позволяет вызывать модуль как функцию и внутри запускает `forward()` вместе со служебной инфраструктурой PyTorch.

## Инженерное назначение

Этот механизм позволяет писать `model(x)` и `block(x)`, сохраняя hooks, autograd и внутренние механизмы PyTorch.

В чтении nanoGPT это объясняет, почему строка `x = block(x)` действительно запускает вычисления блока.

## Причина существования

PyTorch должен не просто вызвать `forward()`, но и обработать дополнительные системные шаги вокруг него.

Если вызывать `forward()` напрямую, часть инфраструктуры PyTorch может быть обойдена.

## Простое объяснение

`model(x)` автоматически вызывает `__call__()`, а `__call__()` затем вызывает `forward()`.

## Как это работает

```text
block(x)
  ↓
nn.Module.__call__()
  ↓
forward()
```

## Пример

```python
output = model(x)
```

Для Transformer Block:

```python
x = block(x)
```

## Типичные ошибки

- Вызывать `forward()` напрямую.
- Считать, что `block(x)` вызывает только `forward()` без инфраструктуры PyTorch.
- Не связывать `block(x)` с объектной моделью `nn.Module`.

## Связанные темы

[[PyTorch/nn.Module|nn.Module]] · [[Transformer Block Interface]] · [[nanoGPT Architecture]]

## Вопросы для проверки

- Почему рекомендуется использовать `model(x)`, а не `model.forward(x)`?
- Что происходит между вызовом объекта и `forward()`?

## Следующие темы

- PyTorch Internal Mechanics
- [[Transformer Block Interface]]
