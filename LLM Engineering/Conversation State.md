---
type: concept
area: LLM Engineering
status: learned
created: 2026-07-10
updated: 2026-07-10
tags: [llm-engineering, context-engineering, state]
aliases: [Dialogue State, Session State]
confidence: high
difficulty: medium
---

# Conversation State

Область: [[LLM Engineering/LLM Engineering|LLM Engineering]]

## Академическое определение

Conversation State — совокупность данных, необходимых приложению для продолжения диалога: истории сообщений, резюме, результатов инструментов, пользовательских настроек и временных переменных.

## Инженерное назначение

Состояние позволяет backend восстанавливать текущий контекст разговора и формировать каждый новый запрос к модели.

## Причина существования

Одной истории сообщений недостаточно для продолжения сложного workflow: приложению также нужны структурированные параметры, промежуточные результаты и сведения о текущей задаче.

## Простое объяснение

Conversation Memory хранит разговор, а Conversation State включает разговор и остальные данные текущей сессии.

## Как это работает

```text
Conversation State
├── Messages
├── Summary
├── User Settings
├── Tool Results
├── Current Project
└── Temporary Variables
```

Backend сохраняет эти части раздельно и передаёт модели только релевантное представление состояния.

## Пример

```python
conversation_state = {
    "current_project": "Restaurant App",
    "preferred_language": "ru",
    "messages": messages,
    "tool_results": tool_results,
}
```

## Типичные ошибки

- Путать Conversation State с историей сообщений.
- Хранить важные переменные только внутри свободного текста переписки.
- Передавать модели всё состояние без отбора.

## Связанные темы

[[Conversation Memory]] · [[Memory Management]] · [[AI Agents/AI Agents|AI Agents]]

## Вопросы для проверки

- Чем Conversation State отличается от Conversation Memory?
- Какие данные кроме истории могут входить в состояние?

## Следующие темы

[[Memory Management]]
