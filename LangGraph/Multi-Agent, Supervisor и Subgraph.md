---
type: concept
area: LangGraph
status: learned
created: 2026-06-26
updated: 2026-06-26
tags:
  - langgraph
confidence: 0.91
---

# Multi-Agent, Supervisor и Subgraph

## Простое объяснение
Supervisor распределяет задачи, Subgraph инкапсулирует сложные процессы.

## Зачем это нужно
Это production-архитектура крупных AI-систем.

## Как это работает
[[Supervisor]] выбирает исполнителя, [[Multi-Agent]] система делит работу между агентами, а [[Subgraph]] прячет сложный workflow за одним узлом.

## Пример
Recipe Agent + Calories Agent + Final LLM.

## Типичные ошибки
- Думать, что каждый Agent обязательно отдельная LLM.

## Вопросы для проверки
- Когда использовать Subgraph?
- Что делает Supervisor?

## Следующие темы
- [[Production Architecture]]

## Связанные темы
[[Planner]] · [[Production Architecture]]
