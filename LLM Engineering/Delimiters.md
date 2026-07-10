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
difficulty: easy
aliases:
  - Prompt Delimiters
  - Context Delimiters
---

# Delimiters

## Академическое определение

Delimiter — структурный разделитель внутри prompt, явно отделяющий инструкции, контекст, примеры и пользовательские данные.

## Инженерное назначение

Delimiters уменьшают неоднозначность интерпретации разных частей prompt.

## Причина существования

Transformer воспринимает вход как последовательность токенов, поэтому логические границы должны быть заданы явно.

## Простое объяснение

Delimiter обозначает, где заканчивается один блок данных и начинается другой.

## Как это работает

```text
Инструкция
↓
Delimiter
↓
Контекст
↓
Delimiter
↓
Задача
```

## Пример

```text
<context>
...
</context>

<question>
...
</question>
```

## Типичные ошибки

- Смешивать инструкции и данные.
- Использовать множество разных стилей разделителей в одном prompt.

## Связанные темы

[[Prompt Engineering]] · [[Prompt Templates]] · [[RAG/Index|RAG]]

## Вопросы для проверки

- Зачем нужны Delimiters?
- Почему они уменьшают неоднозначность?

## Следующие темы

- [[Output Formatting]]
