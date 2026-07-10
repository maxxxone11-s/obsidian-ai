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
  - max_output_tokens
  - Output Token Limit
---

# Max Tokens

## Академическое определение

Max Tokens — параметр генерации, задающий максимальное количество токенов, которое модель может сгенерировать в ответе.

## Инженерное назначение

Max Tokens ограничивает длину ответа, стоимость запроса, время генерации и защищает приложение от чрезмерно длинных ответов.

## Причина существования

Без ограничения длины ответа модель может генерировать больше токенов, чем необходимо, увеличивая стоимость и latency.

## Простое объяснение

Это верхний предел длины ответа. Если модель достигнет лимита, генерация остановится, даже если мысль ещё не закончена.

## Как это работает

```text
Backend задает max_tokens
    ↓
LLM начинает генерацию
    ↓
Счетчик токенов увеличивается
    ↓
Достигнут лимит
    ↓
Генерация прекращается
```

## Пример

```python
response = client.chat.completions.create(
    model="...",
    messages=[...],
    max_tokens=300,
)
```

## Типичные ошибки

- Считать, что `max_tokens` ограничивает размер входного запроса.
- Ожидать, что модель обязательно использует весь лимит.
- Ставить слишком маленькое значение и получать оборванные ответы.

## Связанные темы

[[Messages как источник контекста модели]] · [[Transformers/Context Window vs KV Cache|Context Window]] · [[Transformers/Temperature Sampling|Temperature]] · [[Top-p (Nucleus Sampling)]]

## Вопросы для проверки

- Что ограничивает `max_tokens`?
- Почему `max_tokens` уменьшает стоимость запросов?
- Что произойдет при достижении лимита?

## Следующие темы

- [[Stop Sequence]]
- Context Window
- Cost Optimization
