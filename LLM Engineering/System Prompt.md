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
  - Developer Prompt
  - System Message
---

# System Prompt

## Академическое определение

System Prompt — сообщение разработчика, определяющее постоянные правила поведения модели независимо от пользовательского запроса.

## Инженерное назначение

System Prompt централизованно задаёт роль, стиль, ограничения и формат поведения модели для всех запросов.

## Причина существования

Он отделяет постоянные инструкции приложения от изменяемых пользовательских данных.

## Простое объяснение

System Prompt описывает, как должна вести себя модель, а не что должен получить конкретный пользователь.

## Как это работает

```text
Developer
    ↓
System Prompt
    ↓
User Prompt
    ↓
LLM
```

## Пример

```text
Ты senior Python engineer.
Отвечай кратко.
Не выдумывай информацию.
```

## Типичные ошибки

- Помещать пользовательские данные в System Prompt.
- Изменять System Prompt для каждого пользователя.
- Использовать System Prompt вместо User Prompt.

## Связанные темы

[[Prompt Engineering]] · [[User Prompt]] · [[Prompt Templates]]

## Вопросы для проверки

- Кто формирует System Prompt?
- Что должно находиться в System Prompt?

## Следующие темы

- [[User Prompt]]
- [[Prompt Templates]]
