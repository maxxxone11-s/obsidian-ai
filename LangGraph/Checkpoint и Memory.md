---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - langgraph
confidence: 0.94
---

# Checkpoint и Memory

## Простое объяснение

Checkpoint = где я сейчас, Memory = что я знаю.

## Зачем это нужно

Это основа долгоживущих агентов, которые могут продолжать работу после паузы.

## Как это работает

[[Checkpoint]] сохраняет техническое состояние выполнения графа. [[Checkpoint и Memory|Memory]] хранит долговременные сведения, которые полезны в будущих взаимодействиях.

## Пример

Resume после Interrupt: граф продолжает выполнение с сохранённого места.

## Типичные ошибки

- Путать Checkpoint с Memory.

## Вопросы для проверки

- Что хранит Checkpoint?
- Чем отличается Memory?

## Следующие темы

- [[Human-in-the-loop]]

## Связанные темы

- [[Interrupt]] · [[Resume]]
