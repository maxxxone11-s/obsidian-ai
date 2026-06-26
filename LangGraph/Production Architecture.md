---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - langgraph
confidence: 0.9
---

# Production Architecture

## Простое объяснение
Не один большой агент, а система маленьких компонентов.

## Зачем это нужно
Позволяет масштабировать AI-приложения и поддерживать их без хаоса.

## Как это работает
Production-система обычно сочетает [[Supervisor]], [[Subgraph]], [[Tool]], [[Memory]], [[Checkpoint]] и финальную LLM-генерацию.

## Пример
Supervisor → Subgraph → Tool → Memory → Final LLM.

## Типичные ошибки
- Делать одного огромного агента с огромным prompt.

## Вопросы для проверки
- Почему production редко строят на одном Agent?

## Следующие темы
- [[Практика LangGraph]]

## Связанные темы
[[Multi-Agent]] · [[State]]
