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
difficulty: easy
aliases:
  - OpenRouter SDK
  - OpenAI Compatible API
  - base_url
---

# OpenRouter через OpenAI SDK

Область: [[LLM Engineering/LLM Engineering|LLM Engineering]]

## Академическое определение

OpenRouter предоставляет API, совместимое с OpenAI SDK.

Для работы используется тот же клиент OpenAI, но с указанием собственного `base_url` и API-ключа OpenRouter.

## Инженерное назначение

Эта схема позволяет использовать единый SDK для работы с моделями различных провайдеров без изменения клиентского кода.

Приложение продолжает вызывать familiar API, а маршрутизация к конкретному провайдеру происходит через OpenRouter.

## Причина существования

Унифицированный интерфейс избавляет приложение от необходимости реализовывать отдельную интеграцию для каждого поставщика моделей.

Без OpenAI-compatible слоя код приложения быстро обрастал бы отдельными клиентами, форматами запросов и обработчиками ответов.

## Простое объяснение

OpenAI SDK отправляет запросы не в OpenAI, а в OpenRouter.

OpenRouter самостоятельно перенаправляет их выбранному провайдеру.

## Как это работает

```text
OpenAI()
    ↓
base_url=https://openrouter.ai/api/v1
    ↓
chat.completions.create()
    ↓
OpenRouter
    ↓
Выбранный провайдер
    ↓
Ответ модели
```

## Пример

```python
client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key=os.getenv("OPENROUTER_API_KEY"),
)

response = client.chat.completions.create(
    model="openai/gpt-4o-mini",
    messages=[...],
)
```

## Типичные ошибки

- Хранить API-ключ непосредственно в коде.
- Не использовать `base_url` при работе с OpenRouter.
- Считать, что OpenRouter требует отдельный SDK.
- Путать совместимость SDK с полной идентичностью поведения всех провайдеров.

## Связанные темы

[[Архитектура OpenAI SDK]] · [[Цепочка выполнения chat.completions.create]] · [[Messages как источник контекста модели]] · [[Python Backend/FastAPI|FastAPI]]

## Вопросы для проверки

- Почему для OpenRouter достаточно изменить только `base_url`?
- Какие преимущества дает совместимость с OpenAI SDK?
- Почему API-ключ нельзя хранить прямо в коде?

## Следующие темы

- [[Messages как источник контекста модели]]
- [[Цепочка выполнения chat.completions.create]]
- Parameters
