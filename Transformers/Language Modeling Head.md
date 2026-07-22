---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-03
updated: 2026-07-04
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - Output Projection
  - Language Modeling Head
  - LM Head
---

# Language Modeling Head

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

Language Modeling Head — финальный линейный слой, который преобразует последний контекстный embedding из пространства признаков модели в пространство словаря.

Он выдает logits для всех токенов словаря.

При [[Weight Tying]] LM Head может использовать ту же матрицу весов, что и [[Embedding Layer]].

## Инженерное назначение

Language Modeling Head нужен, чтобы получить оценку следующего токена для каждого элемента словаря.

В LLM inference это мост между внутренним представлением Transformer и алгоритмом генерации текста.

Если используется Weight Tying, этот мост также поддерживает согласованность между входным token embedding space и выходным vocabulary space.

## Причина существования

Transformer строит признаки, но сам по себе не выбирает следующий токен.

Нужен слой, который переводит final embedding в оценки по словарю модели.

Так как вход и выход связаны с одним словарём токенов, в GPT-подобных моделях часто выгодно использовать одну и ту же embedding matrix для входа и выхода.

## Простое объяснение

Последний embedding превращается в оценки для всех возможных токенов.

Затем Softmax и sampling превращают эти оценки в выбор следующего токена.

При Weight Tying это похоже на сравнение финального embedding со всеми токенами словаря в общем пространстве.

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

С Weight Tying:

```text
Final Embedding @ token_embedding_matrix.T -> Logits
```

## Типичные ошибки

- Считать, что Transformer сразу выдает слово.
- Путать logits с вероятностями.
- Путать Language Modeling Head с [[Feed Forward Network]] внутри Transformer Block.
- Считать LM Head независимой таблицей признаков, когда используется [[Weight Tying]].
- Считать последний embedding embedding-ом конкретного слова.

## Связанные темы

[[Transformer Block]] · [[Embedding Layer]] · [[Weight Tying]] · [[Neural Networks/Logits|Logits]] · [[Neural Networks/Softmax|Softmax]] · [[Temperature Sampling]] · [[Autoregressive Generation]]

## Вопросы для проверки

- Зачем нужен последний Linear?
- Что такое logits?
- Почему Softmax применяется после Linear?
- Как Weight Tying связывает Token Embedding и LM Head?

## Следующие темы

- [[Temperature Sampling]]
- [[Weight Tying]]
- Top-k Sampling
- Top-p Sampling
