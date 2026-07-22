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
  - JSON Schema Standard
---

# JSON Schema

Область: [[LLM Engineering/LLM Engineering|LLM Engineering]]

## Академическое определение

JSON Schema — стандарт описания структуры JSON-документов, определяющий допустимые поля, типы, обязательность и ограничения.

## Инженерное назначение

JSON Schema позволяет API проверять корректность структуры данных.

## Причина существования

JSON определяет синтаксис, но не описывает допустимую структуру данных.

## Простое объяснение

JSON Schema — это контракт, описывающий форму JSON.

## Как это работает

```text
Schema
    ↓
Validation
    ↓
Valid JSON Structure
```

## Пример

```text
type: object
properties:
  name: string
  age: integer
```

## Типичные ошибки

- Путать JSON и JSON Schema.
- Считать JSON Schema проверкой бизнес-логики.

## Связанные темы

[[Structured Output]] · [[Pydantic в Structured Output]] · [[LLM Engineering/Response Validation]] · [[Python Backend/FastAPI|FastAPI]]

## Вопросы для проверки

- Чем JSON отличается от JSON Schema?
- Что проверяет JSON Schema?

## Следующие темы

- [[Pydantic в Structured Output]]
