---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - langgraph
confidence: 0.95
---

# StateGraph

## Простое объяснение

StateGraph хранит Node, Edge и маршруты.

## Зачем это нужно

Позволяет собрать отдельные функции в исполняемый граф.

## Как это работает

Через StateGraph задают схему [[State]], добавляют [[Node]], соединяют их через [[Edge]] и компилируют граф.

## Пример

```python
builder = StateGraph(State)
```

## Типичные ошибки

- Путать StateGraph с обычной функцией.

## Вопросы для проверки

- Чем отличается Function от StateGraph?

## Следующие темы

- [[START, END и invoke()]]

## Связанные темы

- [[invoke()]] · [[START и END]]
