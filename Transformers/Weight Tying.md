---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-04
updated: 2026-07-04
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Shared Embedding Matrix
  - Weight Sharing
  - Token Embedding LM Head Sharing
---

# Weight Tying

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

Weight Tying — приём, при котором Token Embedding и [[Language Modeling Head]] используют одну и ту же матрицу весов.

Это позволяет работать в едином пространстве представлений токенов.

## Инженерное назначение

Weight Tying сокращает количество параметров модели и поддерживает согласованность пространства входных и выходных представлений.

Одна матрица используется и для получения embedding токена на входе, и для вычисления logits по словарю на выходе.

## Причина существования

Если embedding хорошо представляет токен на входе, то это же пространство можно использовать для оценки соответствия выходного представления каждому токену словаря.

Без Weight Tying модель держала бы две отдельные большие матрицы для близких по смыслу задач.

## Простое объяснение

Одна и та же таблица используется дважды:

```text
Token -> Embedding
Embedding -> Logits
```

## Как это работает

На входе token id выбирает строку матрицы embedding.

На выходе последний embedding сравнивается со всеми представлениями токенов через ту же матрицу весов.

```text
token_id
    ↓
embedding_matrix[token_id]

final_embedding
    ↓
final_embedding @ embedding_matrix.T
    ↓
logits
```

## Пример

В GPT-подобной модели `wte.weight` может использоваться как матрица token embedding и одновременно как вес выходной проекции LM Head.

## Типичные ошибки

- Считать LM Head независимой таблицей признаков.
- Считать Weight Tying исключительно оптимизацией памяти.
- Думать, что последний embedding является embedding конкретного слова.
- Путать logits с готовым token id.

## Связанные темы

[[Embedding Layer]] · [[Language Modeling Head]] · [[Neural Networks/Logits|Logits]] · [[Embedding Space]]

## Вопросы для проверки

- Почему Token Embedding и LM Head могут использовать одну матрицу?
- Почему последний embedding нельзя считать embedding конкретного слова?
- Как Weight Tying влияет на число параметров?
- Почему выходные logits можно получить через ту же embedding matrix?

## Следующие темы

- Vocabulary Projection
- [[Language Modeling Head]]
- [[Temperature Sampling]]
