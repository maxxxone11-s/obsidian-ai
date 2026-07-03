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
  - Output Projection
  - Language Modeling Head
---

# Language Modeling Head

## Академическое определение

Language Modeling Head — финальный линейный слой, который преобразует последний контекстный embedding из пространства признаков модели в пространство словаря.

Он выдает logits для всех токенов словаря.

## Инженерное назначение

Language Modeling Head нужен, чтобы получить оценку следующего токена для каждого элемента словаря.

В LLM inference это мост между внутренним представлением Transformer и алгоритмом генерации текста.

## Причина существования

Transformer строит признаки, но сам по себе не выбирает следующий токен.

Нужен слой, который переводит final embedding в оценки по словарю модели.

## Простое объяснение

Последний embedding превращается в оценки для всех возможных токенов.

Затем Softmax и sampling превращают эти оценки в выбор следующего токена.

## Как это работает

```text
Final Embedding
    ↓
Linear(d_model -> vocab_size)
    ↓
Logits
    ↓
Softmax
    ↓
Probability Distribution
    ↓
Sampling
```

## Пример

```text
d_model = 4096
vocab_size = 50000

Linear:
4096 -> 50000
```

## Типичные ошибки

- Считать, что Transformer сразу выдает слово.
- Путать logits с вероятностями.
- Путать Language Modeling Head с [[Feed Forward Network]] внутри Transformer Block.

## Связанные темы

[[Transformer Block]] · [[Neural Networks/Logits|Logits]] · [[Neural Networks/Softmax|Softmax]] · [[Temperature Sampling]]

## Вопросы для проверки

- Зачем нужен последний Linear?
- Что такое logits?
- Почему Softmax применяется после Linear?

## Следующие темы

- [[Temperature Sampling]]
- Top-k Sampling
- Top-p Sampling
