---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - langgraph
  - conditional
  - edge
confidence: 0.96
---

# Conditional Edge

Ребро с условием выбора следующего узла.

## Интуитивное объяснение

Как светофор — в зависимости от сигнала, выбираешь направление.

## Кратко

Edge соединяет Node, Conditional Edge позволяет ветвить граф.

## Простое объяснение

Conditional Edge — это связь, которая выбирает узел на основе условия на State.

Node делает работу, Edge определяет маршрут.

## Зачем это нужно

- Ветвления в workflow
- Условная логика
- Динамические пути выполнения

Именно Conditional Edge делает граф умным и позволяет выбирать разные ветки выполнения.

## Как это работает

### Структура
- Функция для определения условия
- Возвращает имя следующего узла
- Вызывается при достижении узла

Обычный Edge задаёт фиксированный переход. [[Conditional Edge]] вызывает [[Router]], который смотрит на [[State]] и возвращает имя следующего маршрута.

## Пример

```python
def check_condition(state):
    return "yes_node" if state["approved"] else "no_node"

graph.add_conditional_edges("decision", check_condition)
```

`choose_mode` → [[Router]] → `diet` / `fried` / `balance`.

## Типичные ошибки

- Неправильные названия узлов
- Не все пути обработаны
- Бесконечные циклы

- Путать Edge и Router.

## Вопросы для проверки

- Чем отличается обычный Edge от Conditional Edge?

## Следующие темы

- [[Router]]

## Связанные темы

- [[Edge]] — простое соединение
- [[Router]] — маршрутизация
- [[Node]] — выбирает узел
- [[State]] — анализирует State

- [[Router]]
