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
  - Pydantic Integration
  - Single Source of Truth
---

# Pydantic в Structured Output

## Академическое определение

Pydantic в Structured Output — использование Pydantic как единственного описания структуры данных, на основе которого создается JSON Schema, валидируется ответ модели и формируется типизированный Python-объект.

## Инженерное назначение

Pydantic позволяет один раз описать структуру данных и использовать её на всех этапах обработки.

## Причина существования

Такой подход исключает дублирование моделей, JSON Schema и ручного парсинга.

## Простое объяснение

Pydantic становится единственным источником истины для структуры данных.

## Как это работает

```text
Pydantic
    ↓
JSON Schema
    ↓
LLM
    ↓
JSON
    ↓
Pydantic Object
```

## Пример

```python
class User(BaseModel):
    name: str
    age: int
```

## Типичные ошибки

- Работать со словарями вместо моделей.
- Писать JSON Schema вручную без необходимости.

## Связанные темы

[[Structured Output]] · [[JSON Schema]] · [[Validation]] · [[Python Backend/FastAPI|FastAPI]]

## Вопросы для проверки

- Почему Pydantic называют Single Source of Truth?
- Что автоматически строится из Pydantic-модели?

## Следующие темы

- [[Validation]]
