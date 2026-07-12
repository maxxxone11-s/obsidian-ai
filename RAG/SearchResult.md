---
type: concept
area: RAG
status: learned
created: 2026-07-12
updated: 2026-07-12
tags: [rag, retrieval, data-contract]
aliases: [Retrieval Result]
confidence: high
difficulty: beginner
---

# SearchResult

## Академическое определение

SearchResult — объект передачи данных, содержащий найденный документ или chunk, retrieval score и служебные metadata, необходимые следующим компонентам RAG Pipeline.

## Инженерное назначение

Объект задаёт стабильный контракт между retriever, reranker и context builder, сохраняя текст, оценку релевантности и происхождение результата.

## Причина существования

Передача только текста теряет score, идентификатор источника, позицию chunk и metadata. Без этих данных последующие этапы не могут корректно rerank, дедуплицировать, объединять и цитировать результаты.

## Простое объяснение

SearchResult объединяет найденный chunk с его score и информацией об источнике.

## Как это работает

1. Retriever находит подходящий indexed record.
2. Создаёт SearchResult с текстом или Document, score и metadata.
3. [[RAG/Reranking|Reranker]] обновляет порядок или оценку результатов.
4. [[RAG/Context Construction|Context Builder]] использует metadata и текст для формирования контекста.

## Пример

```python
SearchResult(
    text="Отпуск составляет 35 дней",
    score=0.92,
    metadata={"source": "HR_policy.pdf", "page": 12},
)
```

## Типичные ошибки

- Возвращать из retriever только текст.
- Игнорировать retrieval score.
- Путать SearchResult с исходным Document или vector record.
- Приписывать metadata самой LLM вместо инфраструктурного объекта RAG.

## Связанные темы

[[RAG/Retrieval|Retriever]] · [[RAG/Reranking|Reranker]] · [[RAG/Context Construction|Context Builder]] · [[RAG/Chunk|Chunk]]

## Вопросы для проверки

- Почему retriever возвращает SearchResult, а не только строку?
- Чем SearchResult отличается от исходного Document?
- Какие данные кроме текста нужны следующим компонентам?

## Следующие темы

[[RAG/Context Construction|Context Construction]] · [[RAG/Production RAG Pipeline|Production RAG Pipeline]]
