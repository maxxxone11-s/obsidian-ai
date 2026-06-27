---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - langgraph
confidence: 0.98
---

# State Update

## Простое объяснение

LangGraph сам объединяет изменения с текущим [[State]].

## Зачем это нужно

Так Node остаются независимыми, а поддержку графа проще контролировать.

## Как это работает

Вместо мутации всего объекта State узел возвращает словарь с изменёнными ключами. Runtime применяет update к текущему состоянию.

## Пример

```python
def choose_mode(state):
    return {"mode": "diet"}
```

## Типичные ошибки

- Писать `state["mode"] = "diet"; return state` вместо возврата маленького dict.

## Вопросы для проверки

- Почему лучше возвращать dict, а не менять State вручную?

## Следующие темы

- [[Node]]

## Связанные темы

- [[State]]
