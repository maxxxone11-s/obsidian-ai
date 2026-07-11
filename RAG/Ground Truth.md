---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, dataset]
aliases: [Golden Labels, Relevance Labels]
confidence: high
difficulty: beginner
---

# Ground Truth

## Академическое определение

Ground Truth — заранее сформированный эталон, определяющий правильные документы, уровни их релевантности или ожидаемые свойства ответа для конкретного evaluation-запроса.

## Инженерное назначение

Эталон служит объективной базой сравнения при вычислении retrieval-метрик и анализе ошибок системы.

## Причина существования

Без знания правильных документов невозможно определить, что retriever нашёл, пропустил или ошибочно добавил, а значит нельзя корректно вычислить Recall, Precision, Hit Rate, MRR и NDCG.

## Простое объяснение

Ground Truth — заранее известный правильный результат, с которым сравнивается работа системы.

## Как это работает

1. Выбирается репрезентативный пользовательский вопрос.
2. Эксперт или проверенная процедура размечает релевантные документы.
3. При необходимости каждому документу назначается степень релевантности.
4. Разметка фиксируется в evaluation dataset.
5. Результаты retrieval сравниваются с эталоном.

## Пример

Для вопроса заранее размечены документы `Doc7`, `Doc19` и `Doc83`. Найденный список сравнивается именно с этим набором.

## Типичные ошибки

- Путать Ground Truth с ответом LLM.
- Считать, что Ground Truth создаётся самим retriever.
- Вычислять retrieval-метрики без эталонной разметки.
- Использовать нерепрезентативный или устаревший набор эталонов.

## Связанные темы

[[Machine Learning/Accuracy Precision Recall и F1|Recall]] · [[Machine Learning/Accuracy Precision Recall и F1|Precision]] · [[RAG/Mean Reciprocal Rank (MRR)|MRR]] · [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]] · [[RAG/Hit Rate|Hit Rate]]

## Вопросы для проверки

- Что такое Ground Truth?
- Почему без него нельзя корректно вычислить retrieval-метрики?

## Следующие темы

[[LLM-as-a-Judge]] · [[Human Evaluation]]
