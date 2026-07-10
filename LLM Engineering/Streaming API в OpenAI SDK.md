---
type: concept
area: LLM Engineering
status: learned
created: 2026-07-10
updated: 2026-07-10
tags: [llm-engineering, streaming, openai-sdk]
aliases: [stream=True, ChatCompletionChunk]
confidence: high
difficulty: medium
---

# Streaming API в OpenAI SDK

## Академическое определение

В Chat Completions API параметр `stream=True` изменяет результат `chat.completions.create()` на итерируемый поток объектов `ChatCompletionChunk`, содержащих последовательные изменения ответа модели.

## Инженерное назначение

Поток позволяет backend постепенно обрабатывать и передавать ответ вместо ожидания полного завершения генерации.

## Причина существования

Итератор предоставляет естественный интерфейс для обработки длинной генерации по мере поступления данных и уменьшает задержку первого отображения.

## Простое объяснение

Вместо одного готового ответа приложение получает поток небольших chunks.

## Как это работает

1. `create(stream=True)` возвращает поток.
2. Цикл `for` получает очередной `ChatCompletionChunk`.
3. Новая текстовая часть читается из `chunk.choices[0].delta.content`.
4. `None` пропускается, а текст отображается или добавляется к полному ответу.

## Пример

```python
parts = []
for chunk in stream:
    content = chunk.choices[0].delta.content
    if content is not None:
        print(content, end="", flush=True)
        parts.append(content)

full_answer = "".join(parts)
```

## Типичные ошибки

- Использовать `message.content` вместо `delta.content`.
- Не проверять `delta.content` на `None`.
- Не собирать полный ответ, когда он нужен для дальнейшей обработки.
- Не понимать, что response в потоковом режиме становится итератором.

## Связанные темы

[[Streaming]] · [[Streaming при Function Calling]]

## Вопросы для проверки

- Почему при Streaming используется `delta`, а не `message`?
- Что возвращает `create(stream=True)`?
- Зачем при печати может понадобиться `flush=True`?

## Следующие темы

[[Streaming при Function Calling]]
