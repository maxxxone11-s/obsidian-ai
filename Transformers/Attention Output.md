---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: medium
difficulty: hard
aliases:
  - Attention Output
  - Weighted Sum
---

# Attention Output

## Кратко

После вычисления весов внимания модель строит новый embedding: взвешенную сумму Value всех токенов.

## Простое объяснение

Каждый токен берет информацию от остальных токенов согласно Attention Weights.

## Зачем это нужно

Именно здесь embedding становится контекстным.

## Как это работает

Формула:

```text
Output = Attention · V
```

Если:

```text
weights = [0.2, 0.3, 0.5]
```

то:

```text
Output = 0.2V1 + 0.3V2 + 0.5V3
```

## Пример

```python
output = weights @ V
```

## Типичные ошибки

- Думать, что числа embedding должны увеличиваться.
- Сравнивать отдельные координаты embedding.

## Вопросы для проверки

- Почему Output отличается от исходного Embedding?
- Что означает вес `0.58`?

## Следующие темы

- [[Embedding Space]]
- [[MultiheadAttention в PyTorch]]

## Связанные темы

- [[Attention Weights]] · [[Статический и контекстный Embedding]] · [[Embedding Space]]
