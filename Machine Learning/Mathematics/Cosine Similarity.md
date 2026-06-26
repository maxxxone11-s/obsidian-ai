---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - machine-learning
  - mathematics
  - linear-algebra
confidence: 0.95
---

# Cosine Similarity

## Простое объяснение
Главное — куда смотрят векторы.

## Зачем это нужно
Используется в embeddings, поиске и RAG.

## Как это работает
Cosine similarity равен скалярному произведению нормализованных векторов. Если направления совпадают, значение близко к 1.

## Пример
`[1, 1]` и `[100, 100]` → cosine = 1.

## Типичные ошибки
- Путать cosine similarity со скалярным произведением.

## Вопросы для проверки
- Почему cosine similarity лучше скалярного произведения для embeddings?

## Следующие темы
- [[Матрица]]

## Связанные темы
[[Нормализация вектора]] · [[AI Engineering/Embeddings|Embeddings]]
