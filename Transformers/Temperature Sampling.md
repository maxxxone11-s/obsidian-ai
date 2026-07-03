---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-03
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - Temperature Sampling
---

# Temperature Sampling

## Академическое определение

Temperature — параметр алгоритма генерации, который изменяет распределение logits перед применением Softmax.

## Инженерное назначение

Temperature управляет балансом между детерминированностью и разнообразием генерации.

В production LLM-системах этот параметр помогает выбирать режим поведения модели: более точный, более стабильный или более творческий.

## Причина существования

Один и тот же Transformer может использоваться как для точных вычислений, так и для творческой генерации текста.

Temperature позволяет управлять этим поведением без переобучения модели.

## Простое объяснение

Temperature определяет, насколько сильно модель должна доверять собственным оценкам вероятностей.

Низкая temperature делает выбор более предсказуемым. Высокая temperature делает выбор более разнообразным.

## Как это работает

Вместо:

```text
Softmax(Logits)
```

используется:

```text
Softmax(Logits / T)
```

Если `T < 1`, распределение становится более острым, и модель чаще выбирает наиболее вероятный токен.

Если `T > 1`, распределение становится более равномерным, и вероятность выбора альтернатив возрастает.

Temperature применяется после завершения работы Transformer и не является частью архитектуры нейронной сети.

## Пример

```text
Код:
Temperature ≈ 0

Генерация сказки:
Temperature > 1
```

## Типичные ошибки

- Считать Temperature частью Transformer.
- Считать Temperature случайным выбором слов.
- Считать высокую Temperature всегда лучшим выбором.

## Связанные темы

[[Language Modeling Head]] · [[Neural Networks/Logits|Logits]] · [[Neural Networks/Softmax|Softmax]]

## Вопросы для проверки

- Где применяется Temperature?
- Почему для программирования используют низкую Temperature?
- Почему для творческих задач используют более высокую Temperature?

## Следующие темы

- Top-k Sampling
- Top-p Sampling
- Sampling Algorithms
