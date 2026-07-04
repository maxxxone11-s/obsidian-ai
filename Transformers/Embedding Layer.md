---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-04
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - nn.Embedding
  - Embedding Matrix
  - Token Embedding
---

# Embedding Layer

## Академическое определение

Embedding Layer — обучаемая таблица признаков, которая преобразует token id в плотный числовой вектор фиксированной размерности.

В Transformer token embedding обычно складывается с [[Position Embedding]], чтобы объединить информацию о смысле токена и его позиции.

В GPT-подобных моделях token embedding matrix также может использоваться в [[Weight Tying]] вместе с [[Language Modeling Head]].

## Инженерное назначение

Embedding Layer является первым этапом обработки текста в Transformer.

Он переводит дискретные id токенов в непрерывное пространство признаков, с которым могут работать Linear-слои, Attention и MLP.

При Weight Tying эта же матрица помогает переводить финальное представление обратно в logits по словарю.

## Причина существования

Нейронная сеть не понимает номера слов как смысловые признаки. Token id — это только адрес строки в словаре.

Embedding Layer нужен, чтобы заменить произвольный номер токена обучаемым представлением.

Так как входные и выходные операции связаны с одним словарём токенов, одну embedding matrix можно переиспользовать и на выходе модели.

## Простое объяснение

Token ID — это адрес строки.

Embedding Layer работает как таблица поиска:

```text
token_id
    ↓
embedding_matrix[token_id]
    ↓
embedding vector
```

## Как это работает

Embedding не вычисляет вектор по формуле, а извлекает его из обучаемой таблицы.

Если словарь содержит `V` слов, а размерность embedding равна `D`, слой хранит матрицу:

```text
E ∈ R^(V × D)
```

Каждая строка соответствует одному токену словаря.

В GPT-подобной архитектуре итоговый вход в Transformer Block часто строится так:

```python
x = tok_emb + pos_emb
```

Размерность при сложении не увеличивается.

При Weight Tying:

```text
token_id -> token_embedding_matrix[token_id]
final_embedding @ token_embedding_matrix.T -> logits
```

## Пример

```python
embedding = nn.Embedding(10000, 128)
tokens = torch.tensor([15, 928, 4021])
vectors = embedding(tokens)
```

Текст:

```text
"I love AI"
```

После токенизации:

```text
[15, 928, 4021]
```

После `embedding(tokens)` превращается в набор векторов.

## Типичные ошибки

- Считать, что embedding вычисляется формулой.
- Считать token id признаком слова.
- Думать, что embedding фиксирован после создания слоя.
- Путать Token Embedding и [[Position Embedding]].
- Считать, что входная embedding matrix всегда полностью независима от [[Language Modeling Head]].

## Связанные темы

[[Position Embedding]] · [[Статический и контекстный Embedding]] · [[Embedding Space]] · [[Query Key Value]] · [[Weight Tying]] · [[Language Modeling Head]] · [[nanoGPT Architecture]]

## Вопросы для проверки

- Почему token id нельзя использовать как признак?
- Что хранится внутри `nn.Embedding`?
- Что изменяется во время обучения?
- Зачем token embedding складывается с position embedding?
- Как token embedding matrix может использоваться на выходе модели?

## Следующие темы

- [[Position Embedding]]
- [[Weight Tying]]
- [[Статический и контекстный Embedding]]
- [[Query Key Value]]
