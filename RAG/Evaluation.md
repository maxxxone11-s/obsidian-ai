---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, metrics]
aliases: [RAG Evaluation, Evaluation Pipeline]
confidence: high
difficulty: beginner
---

# Evaluation

## Академическое определение

Evaluation — процесс объективной оценки качества отдельных компонентов и итогового поведения RAG-системы с помощью специализированных наборов данных и метрик.

## Инженерное назначение

Evaluation позволяет измерять влияние изменений Chunk Size, Top-K, embedding-модели, Hybrid Search или reranker и принимать решения на основании количественных результатов.

## Причина существования

Субъективное впечатление от нескольких ответов не показывает, стало ли качество системы устойчиво лучше. Retrieval и Generation также допускают разные виды ошибок и требуют раздельной оценки.

## Простое объяснение

Evaluation отвечает на вопрос: «Стала ли система лучше после изменения архитектуры?»

## Как это работает

1. Формируется evaluation dataset с запросами и эталонами.
2. Фиксируется версия RAG pipeline.
3. Система выполняет запросы на одинаковых условиях.
4. Отдельно вычисляются Retrieval Metrics и Generation Metrics.
5. Результаты сравниваются с baseline.
6. Изменение принимается или отклоняется.

## Пример

После замены embedding-модели инженер сравнивает Recall, Precision, MRR, Hit Rate и NDCG до и после изменения, чтобы проверить улучшение retrieval.

## Типичные ошибки

- Оценивать RAG субъективно по принципу «кажется, стало лучше».
- Использовать только одну метрику.
- Не разделять Retrieval Evaluation и Generation Evaluation.
- Менять одновременно несколько компонентов без контролируемого сравнения.

## Связанные темы

[[Retrieval Metrics]] · [[Generation Metrics]] · [[RAG/Ground Truth|Ground Truth]]

## Вопросы для проверки

- Почему Evaluation необходим в production RAG?
- Почему Retrieval и Generation оцениваются разными метриками?

## Следующие темы

[[RAG/Ground Truth|Ground Truth]] · [[Machine Learning/Accuracy Precision Recall и F1|Recall]] · [[Generation Evaluation]]
