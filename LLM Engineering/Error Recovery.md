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
  - Recovery Strategy
  - Retry Strategy
---

# Error Recovery

## Академическое определение

Error Recovery — совокупность стратегий обработки ситуаций, при которых ответ модели не может быть безопасно использован приложением.

## Инженерное назначение

Error Recovery обеспечивает устойчивую работу AI-приложения при ошибках генерации или валидации.

## Причина существования

LLM является внешним сервисом, поэтому приложение должно быть готово к некорректным ответам.

## Простое объяснение

Если Validation не прошла, приложение не должно аварийно завершаться.

## Как это работает

```text
Validation
    ↓
Ошибка
    ↓
Retry или Fallback или сообщение пользователю
```

## Пример

```text
Validation failed
    ↓
Retry
    ↓
Validation
```

## Типичные ошибки

- Завершать приложение при первой ошибке.
- Не предусматривать стратегию восстановления.

## Связанные темы

[[LLM Engineering/Response Validation]] · [[Structured Output]] · [[Python Backend/FastAPI|FastAPI]]

## Вопросы для проверки

- Какие существуют стратегии Error Recovery?
- Почему Validation и Error Recovery всегда идут вместе?

## Следующие темы

- Function Calling
