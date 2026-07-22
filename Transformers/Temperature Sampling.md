---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-08
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - Temperature Sampling
  - Sampling Temperature
---

# Temperature Sampling

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

Temperature — параметр алгоритма генерации, который изменяет распределение logits перед применением Softmax.

## Инженерное назначение

Temperature управляет балансом между детерминированностью и разнообразием генерации.

В production LLM-системах этот параметр помогает выбирать режим поведения модели: более точный, более стабильный или более творческий.

Как API parameter, temperature позволяет менять поведение ответа без изменения модели, prompt или весов.

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

В задачах code generation, JSON, Structured Output и Tool Calling обычно используют низкую temperature, чтобы снизить случайность.

В задачах генерации идей допустимы более высокие значения.

## Пример

```text
Код:
Temperature ≈ 0

Генерация сказки:
Temperature > 1
```

```python
temperature = 0.1  # код, JSON, tool calling
temperature = 1.5  # генерация идей
```

## Типичные ошибки

- Считать Temperature частью Transformer.
- Считать Temperature случайным выбором слов.
- Считать высокую Temperature всегда лучшим выбором.
- Считать, что temperature добавляет модели знания.
- Отождествлять temperature исключительно с "креативностью".
- Одновременно активно настраивать temperature и top_p без необходимости.

## Связанные темы

[[Language Modeling Head]] · [[Neural Networks/Logits|Logits]] · [[Neural Networks/Softmax|Softmax]] · [[LLM Engineering/Top-p (Nucleus Sampling)|Top-p]]

## Вопросы для проверки

- Где применяется Temperature?
- Почему для программирования используют низкую Temperature?
- Почему для творческих задач используют более высокую Temperature?
- Что именно изменяет temperature?
- Чем temperature отличается от top_p?

## Следующие темы

- Top-k Sampling
- [[LLM Engineering/Top-p (Nucleus Sampling)|Top-p Sampling]]
- Sampling Algorithms
