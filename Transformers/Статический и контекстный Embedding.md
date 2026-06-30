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
difficulty: medium
aliases:
  - Static Embedding
  - Contextual Embedding
---

# Статический и контекстный Embedding

## Кратко

Embedding, полученный из `nn.Embedding`, является статическим: один и тот же token id всегда возвращает один и тот же вектор.

После прохождения Self-Attention embedding становится контекстным: один и тот же токен может иметь разные представления в зависимости от предложения.

## Простое объяснение

До Attention:

```text
bank
```

всегда один embedding.

После Attention:

```text
bank(finance)
bank(river)
```

получают разные embedding.

## Зачем это нужно

Благодаря этому Transformer умеет различать значения многозначных слов.

## Как это работает

```text
Initial Embedding
    ↓
Self Attention
    ↓
Новый embedding
    ↓
Self Attention
    ↓
Еще более контекстный embedding
```

## Пример

Предложения:

```text
I went to the bank
The river bank
```

Они начинают с одинакового embedding для `bank`, но после нескольких Attention-слоев получают разные представления.

## Типичные ошибки

- Считать embedding окончательным представлением слова.
- Думать, что Self Attention генерирует новые токены.

## Вопросы для проверки

- Почему один embedding недостаточен?
- Когда embedding становится контекстным?

## Следующие темы

- [[Query Key Value]]
- [[Attention Scores]]

## Связанные темы

- [[Embedding Layer]] · [[Embedding Space]] · [[Attention Output]]
