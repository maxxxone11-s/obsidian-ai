---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-07-11
tags: [machine-learning, metrics, rag, evaluation]
aliases: [Classification Metrics, Precision Metric, Recall Metric]
confidence: high
---

# Accuracy, Precision, Recall и F1

## Академическое определение

Accuracy, Precision, Recall и F1 — метрики качества, вычисляемые из true positive, false positive, true negative и false negative. В retrieval роль positive обычно выполняет релевантный документ из [[RAG/Ground Truth|Ground Truth]].

$$
\text{Precision}=\frac{TP}{TP+FP},\qquad
\text{Recall}=\frac{TP}{TP+FN}
$$

$$
\text{F1}=2\cdot\frac{\text{Precision}\cdot\text{Recall}}{\text{Precision}+\text{Recall}}
$$

## Инженерное назначение

Метрики разделяют разные свойства системы: Accuracy описывает общую долю правильных решений, Precision — чистоту найденного множества, Recall — полноту, а F1 балансирует Precision и Recall.

В RAG Recall показывает долю эталонных документов, найденных retriever, а Precision — долю релевантных документов среди всех возвращённых.

## Причина существования

Одного показателя недостаточно: система может находить почти всё нужное вместе с большим количеством шума или возвращать только точные результаты, пропуская важные документы. Accuracy также может вводить в заблуждение при дисбалансе классов.

## Простое объяснение

Precision спрашивает: «Какая часть найденного действительно полезна?» Recall спрашивает: «Все ли нужные объекты удалось найти?»

## Как это работает

Для retrieval:

1. [[RAG/Ground Truth|Ground Truth]] задаёт правильные документы.
2. [[RAG/Retrieval|Retriever]] возвращает набор кандидатов.
3. Пересечение найденных и эталонных документов образует `TP`.
4. Лишние найденные документы образуют `FP`.
5. Пропущенные эталонные документы образуют `FN`.
6. По этим значениям вычисляются Precision и Recall.

## Пример

Ground Truth содержит три документа, а retrieval вернул пять, из которых два правильные:

- `Recall = 2/3`;
- `Precision = 2/5`.

В классификации те же формулы применяются, например, к обнаружению мошенничества или заболевания.

## Типичные ошибки

- Путать знаменатели Precision и Recall.
- Считать, что Recall учитывает количество лишних документов.
- Считать высокий Precision гарантией высокого Recall.
- Воспринимать Accuracy как универсальную метрику.
- Говорить «релевантный ответ», когда retrieval оценивает релевантный документ.

## Связанные темы

[[Machine Learning/Confusion Matrix|Confusion Matrix]] · [[RAG/Ground Truth|Ground Truth]] · [[RAG/Retrieval|Retrieval]] · [[RAG/Hit Rate|Hit Rate]]

## Вопросы для проверки

- Когда важнее Recall, а когда Precision?
- Почему Precision может быть равен `1` при низком Recall?
- Почему увеличение Top-K часто повышает Recall и снижает Precision?

## Следующие темы

[[RAG/Mean Reciprocal Rank (MRR)|Mean Reciprocal Rank]] · [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]]
