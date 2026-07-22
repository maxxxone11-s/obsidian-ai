---
type: concept
area: LLM Engineering
knowledge_area: LLM Engineering
status: learned
created: 2026-07-10
updated: 2026-07-10
tags:
  - llm-engineering
confidence: high
difficulty: medium
aliases:
  - Response Formatting
  - Output Contract
---

# Output Formatting

Область: [[LLM Engineering/LLM Engineering|LLM Engineering]]

## Академическое определение

Output Formatting — проектирование ожидаемого формата ответа модели, формирующее контракт между LLM и приложением.

## Инженерное назначение

Output Formatting позволяет backend ожидать ответ в заранее определенной форме.

## Причина существования

Приложение работает с форматом данных, а не с произвольным текстом.

## Простое объяснение

Формат ответа является контрактом между моделью и приложением.

## Как это работает

```text
Prompt
    ↓
Требование формата
    ↓
Ответ модели
```

## Пример

```text
Ответь только JSON.
Не используй Markdown.
```

## Типичные ошибки

- Считать, что инструкция "Ответь JSON" гарантирует корректный JSON.
- Использовать Output Formatting вместо [[Structured Output]].

## Связанные темы

[[Prompt Engineering]] · [[Structured Output]] · [[JSON Schema]]

## Вопросы для проверки

- Почему Output Formatting не гарантирует корректную структуру?
- Что означает контракт между моделью и приложением?

## Следующие темы

- [[Structured Output]]
