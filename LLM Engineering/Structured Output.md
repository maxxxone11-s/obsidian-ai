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
  - Structured Responses
---

# Structured Output

## Академическое определение

Structured Output — механизм API, позволяющий получать ответ модели, соответствующий заранее определенной структуре данных.

## Инженерное назначение

Structured Output делает результаты LLM пригодными для непосредственного использования программным кодом.

## Причина существования

Он устраняет необходимость ручного парсинга и восстановления структуры ответа.

## Простое объяснение

Вместо свободного текста приложение получает данные, соответствующие заранее описанной структуре.

## Как это работает

```text
Schema
    ↓
LLM
    ↓
Structured Data
```

## Пример

```text
User
  name
  age
```

## Типичные ошибки

- Путать Structured Output с просьбой "верни JSON".
- Считать обычный JSON гарантией структуры.

## Связанные темы

[[Output Formatting]] · [[JSON Schema]] · [[Pydantic в Structured Output]] · [[Validation]]

## Вопросы для проверки

- Чем Structured Output отличается от Output Formatting?
- Какую проблему он решает?

## Следующие темы

- [[JSON Schema]]
