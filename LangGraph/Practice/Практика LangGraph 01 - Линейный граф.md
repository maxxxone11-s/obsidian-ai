---
type: concept
area: LangGraph
status: learning
created: 2026-06-26
updated: 2026-06-26
tags:
  - langgraph
  - practice
confidence: 0
---

# Линейный граф

## Простое объяснение
Практическое упражнение по LangGraph: Собрать простой граф без ветвлений: START → Node → END.

## Зачем это нужно
Практика закрепляет понимание [[State]], [[Node]], [[Edge]], [[Router]] и runtime-механики графа.

## Как это работает
Сначала проектируется минимальный [[State]], затем добавляются узлы и переходы. После этого граф запускается через [[START, END и invoke()]].

## Пример
Мини-проект: Собрать простой граф без ветвлений: START → Node → END.

## Типичные ошибки
- Начинать с большого агента вместо маленького графа.
- Смешивать логику Node, Router и Tool.
- Менять State напрямую вместо возврата [[State Update]].

## Связанные темы
[[LangGraph Overview]] · [[StateGraph]] · [[State]] · [[Node]]
