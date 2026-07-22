---
type: concept
area: RAG
status: learned
created: 2026-07-12
updated: 2026-07-12
tags: [rag, generation, prompt-construction]
aliases: [Prompt Builder, Prompt Assembly]
confidence: high
difficulty: intermediate
---

# Prompt Construction

Область: [[RAG/RAG|RAG]]

## Академическое определение

Prompt Construction — этап Query Pipeline, объединяющий системные инструкции, подготовленный retrieved context и пользовательский вопрос в единый вход для LLM.

## Инженерное назначение

Этап задаёт правила использования найденного контекста, ограничивает допустимое поведение модели и формирует воспроизводимый интерфейс между RAG-инфраструктурой и LLM.

## Причина существования

LLM получает последовательность токенов и сама не знает, какая часть входа является системной инструкцией, retrieved context или вопросом. Эти части необходимо явно собрать и разграничить.

## Простое объяснение

Prompt Builder собирает итоговый запрос: правила для модели, найденные данные и вопрос пользователя.

## Как это работает

1. Получает System Prompt.
2. Получает Final Context от [[RAG/Context Construction|Context Construction]].
3. Добавляет User Question.
4. Разграничивает инструкции, контекст и пользовательские данные.
5. Передаёт собранный prompt LLM.

## Пример

System Prompt требует отвечать только по источникам, затем вставляется блок Context, а после него — вопрос пользователя.

## Типичные ошибки

- Путать Prompt Construction с общим [[LLM Engineering/Prompt Engineering|Prompt Engineering]].
- Передавать retrieved context без инструкций о его использовании.
- Не отделять недоверенный текст документов от системных инструкций.
- Считать, что хороший retrieval автоматически гарантирует хороший ответ.

## Связанные темы

[[RAG/Context Construction|Context Construction]] · [[RAG/Query Pipeline|Query Pipeline]] · [[LLM Engineering/System Prompt|System Prompt]] · [[LLM Engineering/Prompt Engineering|Prompt Engineering]] · [[RAG/Faithfulness|Faithfulness]]

## Вопросы для проверки

- Почему Prompt Construction существует отдельно от LLM?
- Какие три основные части входят в RAG prompt?
- Почему хороший retrieval не гарантирует хороший ответ?

## Следующие темы

[[RAG/Context Construction|Context Construction]] · [[RAG/Lost in the Middle|Lost in the Middle]]
