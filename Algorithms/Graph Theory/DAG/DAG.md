---
type: concept
area: Algorithms & Data Structures
status: learned
created: 2026-06-27
updated: 2026-06-27
tags:
  - algorithms
  - graph-theory
confidence: 0.92
difficulty: medium
---

# DAG

## Простое объяснение
Есть направление, но невозможно вернуться назад по циклу.

## Зачем это нужно
DAG используется практически во всех современных вычислительных системах.

## Как это работает
DAG означает Directed Acyclic Graph: directed, acyclic, graph. Любой процесс в нём движется вперед без циклического возврата.

## Пример
PyTorch Computation Graph, Git, Python imports, AI Pipelines.

## Типичные ошибки
- Думать, что DAG — отдельная сложная структура, а не обычный граф с ограничениями.

## Ментальная модель
PyTorch Computation Graph — обычный DAG.

## Вопросы для проверки
- Что означает DAG?
- Почему PyTorch использует DAG?
- Почему DAG не может содержать цикл?

## Следующие темы
- [[Представление графов в памяти]]

## Связанные темы
[[PyTorch Computation Graph]] · [[Что такое граф]] · [[Цикл]]
