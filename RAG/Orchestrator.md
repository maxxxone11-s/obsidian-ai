---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, production, orchestration, architecture]
aliases: [RAG Orchestrator, Pipeline Controller]
confidence: high
difficulty: intermediate
---

# Orchestrator

## Академическое определение

Orchestrator — компонент RAG-системы, управляющий порядком вызова независимых pipeline-компонентов и передачей данных между ними.

## Инженерное назначение

Orchestrator координирует Query Transformation, embedding-модель, retriever, reranker, prompt builder и LLM, сохраняя их локальные ответственности и единый control flow.

## Причина существования

Без отдельной оркестрации компоненты вынуждены знать друг о друге и самостоятельно решать, кого вызывать следующим. Это создаёт сильную связанность и усложняет тестирование, замену и развитие pipeline.

## Простое объяснение

Это дирижёр RAG Pipeline: он не ищет документы и не генерирует ответ, а определяет, какой компонент и с какими данными должен выполняться следующим.

## Как это работает

1. Получает вопрос и начальное состояние запроса.
2. Вызывает [[RAG/Query Transformation|Query Transformation]], если запрос нужно уточнить.
3. Передаёт итоговый запрос embedding-модели.
4. Запускает [[RAG/Retrieval|Retriever]] и [[RAG/Reranking|Reranker]].
5. Передаёт выбранный контекст prompt builder.
6. Вызывает LLM и возвращает итоговый ответ.

Оркестрация может быть реализована как последовательный workflow, chain или graph, но эти термины не являются синонимами самого компонента.

## Пример

Orchestrator принимает вопрос, вызывает embedding-модель, затем retriever и reranker, после чего собирает prompt из вопроса и контекста и вызывает LLM.

## Типичные ошибки

- Считать, что Orchestrator сам выполняет retrieval или generation.
- Встраивать поисковую и генеративную логику непосредственно в Orchestrator.
- Создавать сильные прямые зависимости между компонентами.
- Передавать каждому компоненту знания обо всей архитектуре.

## Связанные темы

[[RAG/Query Pipeline|Query Pipeline]] · [[RAG/Query Transformation|Query Transformation]] · [[RAG/Retrieval|Retriever]] · [[RAG/Reranking|Reranker]] · [[Prompt Builder]] · [[LLM Engineering/Production Pipeline LLM-приложения|Production Pipeline LLM-приложения]]

## Вопросы для проверки

- Какую ответственность выполняет Orchestrator?
- Почему retriever и reranker не должны напрямую управлять всем pipeline?
- Чем orchestration отличается от выполнения поиска или генерации?

## Следующие темы

[[RAG/Query Transformation|Query Transformation]] · [[Prompt Builder]]
