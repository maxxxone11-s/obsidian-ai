---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
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

## Кратко

Embedding Layer - первый этап обработки текста в Transformer. Он преобразует идентификатор токена в плотный числовой вектор фиксированной размерности.

## Простое объяснение

Token ID - это адрес строки.

Embedding Layer работает как таблица поиска:

```text
token_id
    ↓
embedding_matrix[token_id]
    ↓
embedding vector
```

## Зачем это нужно

Нейронная сеть не понимает номера слов. ID не содержит семантики, поэтому embedding превращает произвольный номер токена в обучаемое представление слова.

## Как это работает

Embedding не вычисляет вектор по формуле, а извлекает его из обучаемой таблицы.

Если словарь содержит `V` слов, а размерность embedding равна `D`, слой хранит матрицу:

```text
E ∈ R^(V × D)
```

Каждая строка соответствует одному токену словаря.

```python
embedding = nn.Embedding(10000, 128)
tokens = torch.tensor([15, 928, 4021])
vectors = embedding(tokens)
```

`nn.Embedding(10000, 128)` означает таблицу `(10000 x 128)`, где `10000` - размер словаря, а `128` - размер embedding каждого токена.

## Пример

Текст:

```text
"I love AI"
```

После токенизации:

```text
[15, 928, 4021]
```

После `embedding(tokens)` превращается в набор векторов:

```text
[
  [...128...],
  [...128...],
  [...128...]
]
```

Во время обучения обновляется сама таблица embedding.

## Типичные ошибки

- Считать, что embedding вычисляется формулой.
- Считать token id признаком слова.
- Думать, что embedding фиксирован после создания слоя.

## Вопросы для проверки

- Почему token id нельзя использовать как признак?
- Что хранится внутри `nn.Embedding`?
- Что изменяется во время обучения?

## Следующие темы

- [[Статический и контекстный Embedding]]
- [[Query Key Value]]

## Связанные темы

- [[Статический и контекстный Embedding]] · [[Embedding Space]] · [[Query Key Value]]
