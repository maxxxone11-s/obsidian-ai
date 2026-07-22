---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, generation]
aliases: [Response Faithfulness, Groundedness]
confidence: high
difficulty: intermediate
---

# Faithfulness

Область: [[RAG/RAG|RAG]]

## Академическое определение

Faithfulness — метрика Generation Evaluation, оценивающая, насколько утверждения в ответе LLM подтверждаются переданным контекстом.

## Инженерное назначение

Метрика обнаруживает неподтверждённые контекстом утверждения и галлюцинации генератора даже при корректно работающем retrieval.

## Причина существования

Retriever может передать идеальный контекст, однако LLM способна добавить сведения, которых в документах не было. Retrieval-метрики такую ошибку не обнаруживают.

## Простое объяснение

Faithfulness проверяет, придумала ли модель что-либо сверх полученного контекста.

## Как это работает

1. Ответ разбивается на отдельные проверяемые claims.
2. Каждый claim сопоставляется с переданным контекстом.
3. Определяется доля утверждений, которые контекст поддерживает.
4. Результаты агрегируются в итоговую оценку Faithfulness.

## Пример

В контексте сказано, что PostgreSQL появился в 1996 году. Ответ «PostgreSQL появился в 1998 году» снижает Faithfulness, даже если нужный документ был найден корректно.

## Типичные ошибки

- Путать Faithfulness с проверкой абсолютной истинности относительно интернета.
- Считать, что метрика оценивает retrieval.
- Считать, что для Faithfulness всегда необходим [[RAG/Ground Truth|Ground Truth]].
- Приравнивать высокий Faithfulness к полноте и полезности ответа.

## Связанные темы

[[RAG/Answer Relevancy|Answer Relevancy]] · [[RAG/LLM-as-a-Judge|LLM-as-a-Judge]] · [[Hallucination]]

## Вопросы для проверки

- Что именно сравнивает Faithfulness?
- Почему высокий Faithfulness не гарантирует хороший ответ?
- Почему Faithfulness можно оценивать без Ground Truth?

## Следующие темы

[[RAG/Answer Relevancy|Answer Relevancy]]
