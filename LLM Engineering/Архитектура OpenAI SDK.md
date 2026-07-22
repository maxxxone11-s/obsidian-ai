---
type: concept
area: LLM Engineering
knowledge_area: LLM Engineering
status: learned
created: 2026-07-08
updated: 2026-07-08
tags:
  - llm-engineering
confidence: high
difficulty: medium
aliases:
  - SDK Structure
  - Client Resources
---

# Архитектура OpenAI SDK

Область: [[LLM Engineering/LLM Engineering|LLM Engineering]]

## Академическое определение

OpenAI SDK организован по ресурсам API.

Каждый ресурс представлен отдельным объектом, содержащим методы работы с соответствующим endpoint.

## Инженерное назначение

Такая архитектура повторяет структуру REST API и разделяет разные типы ресурсов: chat, images, audio, embeddings и другие.

Это делает SDK расширяемым и удобным для чтения.

## Причина существования

Если бы все методы находились на одном объекте, SDK быстро стал бы перегруженным и плохо масштабировался.

Разделение по ресурсам позволяет добавлять новые API-направления без смешивания несвязанных методов.

## Простое объяснение

`client -> chat -> completions -> create` — это последовательность объектов, а не одна длинная функция.

## Как это работает

```text
client
  ├── chat
  │      └── completions
  │             └── create()
  ├── images
  ├── audio
  └── embeddings
```

## Пример

```python
client.chat.completions.create(...)
client.embeddings.create(...)
client.images.generate(...)
```

## Типичные ошибки

- Воспринимать `client.chat.completions.create` как одну функцию.
- Не понимать соответствие структуры SDK структуре REST API.
- Искать все методы напрямую на объекте `client`.

## Связанные темы

[[OpenRouter через OpenAI SDK]] · [[Цепочка выполнения chat.completions.create]] · [[Python Backend/FastAPI|FastAPI]]

## Вопросы для проверки

- Что представляет собой объект `client`?
- Почему SDK разбит на ресурсы?
- Как структура SDK связана со структурой REST API?

## Следующие темы

- [[Messages как источник контекста модели]]
- Response Object
