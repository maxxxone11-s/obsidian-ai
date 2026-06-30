---
type: concept
area: Transformers
knowledge_area: Transformers
status: needs_review
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: medium
difficulty: hard
aliases:
  - Embedding Space
  - Semantic Space
---

# Embedding Space

## Кратко

Embedding следует рассматривать как точку в многомерном пространстве. Отдельные координаты embedding практически не интерпретируются; важно положение точки относительно других точек.

## Простое объяснение

Attention не делает embedding "больше" или "меньше". Он изменяет положение точки в пространстве признаков.

## Зачем это нужно

Изменение положения embedding позволяет модели учитывать смысл предложения.

## Как это работает

Self Attention постепенно смещает embedding в область пространства, соответствующую текущему контексту.

```text
Начальный embedding
    ↓
Attention
    ↓
Новый embedding
    ↓
Следующий Transformer Block
    ↓
Еще более точное положение в пространстве
```

## Пример

Один и тот же token `bank` после разных контекстов оказывается в разных областях embedding space:

```text
bank(finance)
bank(river)
```

## Типичные ошибки

- Анализировать отдельные координаты embedding.
- Считать изменение числа улучшением embedding.
- Считать, что заранее существует "правильная точка".

## Вопросы для проверки

- Почему нельзя анализировать одну координату embedding?
- Что означает смещение embedding?

## Следующие темы

- [[MultiheadAttention в PyTorch]]
- Transformer Block

## Связанные темы

- [[Embedding Layer]] · [[Статический и контекстный Embedding]] · [[Attention Output]]
