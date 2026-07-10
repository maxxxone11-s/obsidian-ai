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
  - Prompt Template
  - Prompt Files
---

# Prompt Templates

## Академическое определение

Prompt Template — шаблон prompt, отделяющий постоянную структуру запроса от динамически подставляемых данных.

## Инженерное назначение

Prompt Templates позволяют централизованно поддерживать, тестировать и версионировать prompts.

## Причина существования

Они исключают ручную сборку больших prompt-строк и повышают сопровождаемость проекта.

## Простое объяснение

Prompt Template работает похоже на HTML-шаблоны или шаблоны Jinja.

## Как это работает

```text
Template
    ↓
Подстановка данных
    ↓
Готовый Prompt
```

## Пример

```text
Topic: {topic}
Level: {level}
```

## Типичные ошибки

- Собирать большие prompt через конкатенацию строк.
- Хранить все prompts непосредственно в Python-коде.

## Связанные темы

[[Prompt Engineering]] · [[System Prompt]] · [[User Prompt]] · [[Delimiters]]

## Вопросы для проверки

- Почему Prompt Templates удобнее обычных строк?
- Что отделяет Prompt Template?

## Следующие темы

- Prompt Versioning
- [[Few-shot Prompting]]
