---
type: concept
area: RAG
status: learned
created: 2026-07-12
updated: 2026-07-12
tags: [rag, context, prompt-construction, position-bias]
aliases: [Context Position Bias]
confidence: high
difficulty: advanced
---

# Lost in the Middle

## Академическое определение

Lost in the Middle — эффект, при котором LLM использует релевантную информацию в середине длинного prompt менее надёжно, чем информацию ближе к его началу или концу.

## Инженерное назначение

Эффект учитывают при упорядочивании retrieved context, чтобы важные chunks занимали позиции с большей вероятностью использования моделью.

## Причина существования

Доступность большого Context Window не означает равномерного внимания к каждой позиции. Поэтому релевантный документ может быть найден и передан модели, но всё равно слабо повлиять на ответ.

## Простое объяснение

Качество зависит не только от того, какие документы попали в prompt, но и от того, где именно они расположены.

## Как это работает

1. Reranker оценивает релевантность chunks.
2. Context Builder учитывает token budget и позиционный эффект.
3. Наиболее важные fragments размещаются ближе к началу или концу длинного контекста.
4. Менее важные fragments занимают середину либо исключаются.

## Пример

Самые релевантные chunks размещаются по краям Final Context, а менее важные — между ними, чтобы снизить риск потери ключевой информации в середине prompt.

## Типичные ошибки

- Считать, что сортировки reranker достаточно без учёта итоговой позиции в prompt.
- Игнорировать влияние длины и порядка контекста.
- Размещать наиболее релевантный chunk в центре очень длинного prompt.
- Пытаться компенсировать плохой context construction только увеличением Context Window.

## Связанные темы

[[RAG/Prompt Construction|Prompt Construction]] · [[RAG/Context Construction|Context Construction]] · [[RAG/Reranking|Reranker]] · [[LLM Engineering/Context Window|Context Window]]

## Вопросы для проверки

- Почему идеальный reranker не гарантирует использование лучшего chunk?
- Как позиция документа влияет на генерацию?
- Почему увеличение Context Window не устраняет эффект автоматически?

## Следующие темы

[[RAG/Ingestion Pipeline|Ingestion Pipeline]] · [[RAG/Production RAG Pipeline|Production RAG Pipeline]]
