---
type: concept
area: LLM Engineering
status: learned
created: 2026-07-10
updated: 2026-07-10
tags: [llm-engineering, streaming, function-calling]
aliases: [Tool Streaming, Streaming Tool Calls]
confidence: high
difficulty: hard
---

# Streaming при Function Calling

## Академическое определение

Streaming при Function Calling — потоковый режим, в котором API передаёт не только текст, но и структурированные фрагменты tool call, которые backend собирает до полного формирования вызова.

## Инженерное назначение

Режим объединяет потоковую генерацию и Function Calling в одном процессе, сохраняя возможность постепенно обрабатывать события модели.

## Причина существования

Имя инструмента и его аргументы также генерируются моделью постепенно, поэтому API может передавать их частями, как и обычный текст.

## Простое объяснение

Во время Streaming backend получает события разных типов: части текста и части вызова инструмента.

## Как это работает

1. Первый stream передаёт фрагменты tool call.
2. Backend объединяет фрагменты имени и аргументов по идентификатору вызова.
3. Только после завершения сборки backend валидирует аргументы и вызывает функцию.
4. Tool result добавляется в историю.
5. Второй вызов LLM может потоково передать текстовый ответ пользователю.

## Пример

```text
LLM stream → chunks аргументов {"city":"Berlin"}
Backend → сборка и валидация → get_weather("Berlin")
Tool result → LLM stream → текстовые chunks ответа
```

## Типичные ошибки

- Считать, что Streaming всегда содержит только текст.
- Начинать выполнять функцию до завершения сборки tool call.
- Не различать текстовые события и события Tool Calling.

## Связанные темы

[[Streaming]] · [[Tool Loop]] · [[Function Calling]]

## Вопросы для проверки

- Какие типы данных могут приходить во время Streaming?
- Почему tool call передаётся по частям?
- Когда backend может безопасно вызвать функцию?

## Следующие темы

[[Transformers/Context Window vs KV Cache|Context Window]]
