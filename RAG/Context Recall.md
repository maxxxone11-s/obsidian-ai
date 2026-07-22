---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, context]
aliases: [Context Coverage]
confidence: high
difficulty: intermediate
---

# Context Recall

Область: [[RAG/RAG|RAG]]

## Академическое определение

Context Recall — метрика, оценивающая, содержит ли переданный LLM контекст всю информацию, необходимую для построения полного эталонного ответа.

## Инженерное назначение

Метрика помогает обнаружить недостаточность итогового контекста и отделить потерю информации до генерации от ошибок самой LLM.

## Причина существования

Модель не может использовать сведения, которые не попали в context. Высокий Faithfulness при этом возможен: ответ будет основан на контексте, но останется неполным.

## Простое объяснение

Context Recall показывает, хватило ли модели переданной информации для полного ответа.

## Как это работает

1. Определяется информация, необходимая для эталонного ответа.
2. Проверяется, какая её часть присутствует в переданном контексте.
3. Покрытие агрегируется в итоговую оценку.
4. Низкое значение указывает на недостаточный retrieval, Top-K или сборку контекста.

## Пример

Для полного ответа нужны три chunks, но LLM получила только один. Ответ может быть полностью faithful этому chunk, однако Context Recall будет низким.

## Типичные ошибки

- Путать Context Recall с Retrieval Recall.
- Считать высокий Faithfulness гарантией полноты ответа.
- Оценивать Context Recall без определения необходимой информации.

## Связанные темы

[[RAG/Context Precision|Context Precision]] · [[RAG/Faithfulness|Faithfulness]] · [[Machine Learning/Accuracy Precision Recall и F1|Retrieval Recall]]

## Вопросы для проверки

- Чем Context Recall отличается от Retrieval Recall?
- Почему Faithfulness может быть высоким при низком Context Recall?
- Почему уменьшение Top-K способно ухудшить Context Recall?

## Следующие темы

[[Production RAG Pipeline]]
