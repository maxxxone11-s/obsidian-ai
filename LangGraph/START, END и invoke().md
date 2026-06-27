---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - langgraph
confidence: 0.96
---

# START, END и invoke()

## Простое объяснение

`invoke()` принимает начальный [[State]] и возвращает итоговый State.

## Зачем это нужно

Это жизненный цикл любого графа LangGraph.

## Как это работает

[[START и END]] обозначают границы графа. После компиляции `graph.invoke(initial_state)` запускает выполнение от START до END.

## Пример

```python
result = graph.invoke({"user_input": "Что приготовить?"})
```

## Типичные ошибки

- Думать, что invoke() принимает только строку пользователя.

## Вопросы для проверки

- Что возвращает invoke()?

## Следующие темы

- [[Checkpoint и Memory]]

## Связанные темы

- [[StateGraph]]
