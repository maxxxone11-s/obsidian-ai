---
type: concept
area: RAG
status: learned
created: 2026-07-11
updated: 2026-07-11
tags: [rag, evaluation, ranking]
aliases: [MRR, Reciprocal Rank]
confidence: high
difficulty: intermediate
---

# Mean Reciprocal Rank (MRR)

Область: [[RAG/RAG|RAG]]

## Академическое определение

Mean Reciprocal Rank — метрика ранжирования, равная среднему обратному рангу первого релевантного результата по множеству запросов:

$$
\operatorname{MRR}=\frac{1}{|Q|}\sum_{q\in Q}\frac{1}{\operatorname{rank}_q}
$$

## Инженерное назначение

MRR измеряет, насколько высоко система обычно располагает первый релевантный документ.

## Причина существования

Precision и Recall оценивают состав найденного множества, но не учитывают позицию первого полезного результата.

## Простое объяснение

Чем выше первый правильный документ, тем больше оценка. Затем оценки усредняются по всем запросам.

## Как это работает

1. Для каждого запроса находится позиция первого релевантного документа.
2. Вычисляется `Reciprocal Rank = 1 / rank`.
3. Если релевантных документов нет, значение равно `0`.
4. Значения усредняются по evaluation dataset.

## Пример

Если первый релевантный документ находится на втором месте, `RR = 1/2 = 0.5`. Для позиций `1`, `2` и отсутствия результата MRR равен `(1 + 0.5 + 0) / 3 = 0.5`.

## Типичные ошибки

- Путать Rank и Reciprocal Rank.
- Считать, что MRR учитывает все релевантные документы.
- Вычислять MRR по одному запросу и называть результат средним.

## Связанные темы

[[Machine Learning/Accuracy Precision Recall и F1|Recall]] · [[Machine Learning/Accuracy Precision Recall и F1|Precision]] · [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]]

## Вопросы для проверки

- Почему MRR оценивает только первый релевантный документ?
- Что означает Reciprocal Rank?

## Следующие темы

[[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]]
