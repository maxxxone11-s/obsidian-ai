---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - Skip Connection
  - Residual Link
  - Identity Connection
---

# Residual Connection

## Кратко

После Self-Attention Transformer не заменяет исходный embedding новым. Вместо этого используется остаточная связь.

## Простое объяснение

Attention не переписывает embedding. Он добавляет к нему новую информацию.

## Зачем это нужно

Residual Connection сохраняет исходную информацию даже после большого количества Transformer Block. Каждый блок постепенно уточняет embedding вместо полного переписывания.

## Как это работает

Формула:

```text
y = x + Attention(x)
```

где `x` - исходный embedding, а `Attention(x)` - информация, полученная после механизма внимания.

Если:

```text
x = [2, 5]
Attention(x) = [1, -2]
```

то:

```text
Output = [2, 5] + [1, -2] = [3, 3]
```

Исходный embedding остается частью нового представления.

## Пример

Вместо:

```python
x = attention(x)
```

используется:

```python
x = x + attention(x)
```

## Типичные ошибки

- Считать, что Attention полностью заменяет embedding.
- Считать Residual Connection механизмом обучения.
- Путать Residual Connection с Backpropagation.

## Вопросы для проверки

- Почему нельзя просто заменить embedding результатом Attention?
- Что сохраняет Residual Connection?
- Почему глубокие Transformer используют Residual?

## Следующие темы

- [[LayerNorm]]
- [[Постепенное уточнение embedding]]

## Связанные темы

- [[Transformer Block]] · [[LayerNorm]] · [[Feed Forward Network]]
