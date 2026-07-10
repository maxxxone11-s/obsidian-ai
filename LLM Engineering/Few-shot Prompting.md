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
  - Few-shot
  - In-context Examples
---

# Few-shot Prompting

## Академическое определение

Few-shot Prompting — техника Prompt Engineering, при которой в контекст запроса добавляются несколько эталонных примеров входных и выходных данных.

## Инженерное назначение

Few-shot уменьшает неоднозначность задачи и повышает стабильность поведения модели.

## Причина существования

Несколько примеров помогают модели продолжить уже сформированный шаблон поведения.

## Простое объяснение

Модель не обучается, а получает примеры внутри текущего контекста.

## Как это работает

```text
Примеры
    ↓
Новый вход
    ↓
Продолжение по шаблону
```

## Пример

```text
EN: Hello
RU: Привет

EN: Thank you
RU: Спасибо
```

## Типичные ошибки

- Считать Few-shot обучением модели.
- Использовать противоречивые примеры.
- Добавлять слишком много примеров без необходимости.

## Связанные темы

[[Prompt Engineering]] · [[Prompt Templates]] · [[Delimiters]]

## Вопросы для проверки

- Чем Few-shot отличается от обучения модели?
- Когда Few-shot наиболее полезен?

## Следующие темы

- [[Delimiters]]
- [[Structured Output]]
