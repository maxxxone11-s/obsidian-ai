---
type: concept
area: ai-agents
status: draft
created: 2026-06-26
updated: 2026-06-26
tags: [langgraph, state, data]
confidence: 0
---

# State

Состояние графа в LangGraph.

## Простое объяснение

State — это данные, которые передаются между узлами графа в LangGraph.

## Интуитивное объяснение

Как контекст в разговоре — информация, которую нужно помнить и передавать между этапами.

## Зачем это нужно

- Управление данными в workflow
- Передача информации между узлами
- Отслеживание прогресса

## Как это работает

### Структура
- Может быть простой переменной или сложным объектом
- Обновляется при переходе между узлами

## Пример

```python
from langgraph.graph import StateGraph
from typing import TypedDict

class AgentState(TypedDict):
    messages: list
    context: str

graph = StateGraph(AgentState)
```

## Типичные ошибки

- Неправильная структура State
- Мутирование State без необходимости
- Забывают про типизацию

## Связанные темы

- [[Node]] — узлы работают с State
- [[Edge]] — передают State
- [[Router]] — маршрутизирует по State

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
