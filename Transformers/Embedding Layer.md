---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-06
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - nn.Embedding
  - Embedding Matrix
  - Token Embedding
  - Embedding Lookup Table
  - Token Embedding Matrix
  - Trainable Embedding Table
---

# Embedding Layer

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

Embedding Layer — обучаемая таблица признаков, которая преобразует token id в плотный числовой вектор фиксированной размерности.

В PyTorch `nn.Embedding` является полноценным обучаемым слоем, а не просто двумерной матрицей чисел.

В Transformer token embedding обычно складывается с [[Position Embedding]], чтобы объединить информацию о смысле токена и его позиции.

В GPT-подобных моделях token embedding matrix также может использоваться в [[Weight Tying]] вместе с [[Language Modeling Head]].

## Инженерное назначение

Embedding Layer является первым этапом обработки текста в Transformer.

Он переводит дискретные id токенов в непрерывное пространство признаков, с которым могут работать Linear-слои, Attention и MLP.

`nn.Embedding` нужен, чтобы быстро получать embedding по индексу без вычисления через Linear Layer и одновременно автоматически регистрировать таблицу как часть модели.

При Weight Tying эта же матрица помогает переводить финальное представление обратно в logits по словарю.

## Причина существования

Нейронная сеть не понимает номера слов как смысловые признаки. Token id — это только адрес строки в словаре.

Embedding Layer нужен, чтобы заменить произвольный номер токена обучаемым представлением.

Каждому токену требуется собственный обучаемый embedding, который будет изменяться во время обучения модели.

Отдельный класс `nn.Embedding` нужен потому, что обычный Tensor не интегрирован в жизненный цикл `nn.Module`: его сложнее автоматически обучать, сохранять и переносить между устройствами.

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

При вызове `embedding(idx)` PyTorch не выполняет Attention или Linear. Он возвращает строку таблицы с номером `idx`.

Если словарь содержит `V` слов, а размерность embedding равна `D`, слой хранит матрицу:

```text
E ∈ R^(V × D)
```

Каждая строка соответствует одному токену словаря.

Как обучаемый слой `nn.Embedding` автоматически:

- входит в `model.parameters()`;
- получает gradients;
- обновляется через `optimizer.step()`;
- сохраняется в `state_dict`;
- переносится через `model.to(device)`.

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

Для nanoGPT-подобной модели:

```python
embedding = nn.Embedding(50304, 768)
vector = embedding(torch.tensor([15496]))
```

Это возвращает строку с индексом `15496` размерности `768`.

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
- Искать сложные вычисления там, где выполняется обычный lookup по таблице.
- Считать `nn.Embedding` обычным Tensor.
- Считать token id признаком слова.
- Думать, что embedding фиксирован после создания слоя.
- Считать, что внутри `nn.Embedding` происходит проход через Transformer.
- Путать Token Embedding и [[Position Embedding]].
- Считать, что входная embedding matrix всегда полностью независима от [[Language Modeling Head]].

## Связанные темы

[[Position Embedding]] · [[Статический и контекстный Embedding]] · [[Embedding Space]] · [[Query Key Value]] · [[Weight Tying]] · [[Language Modeling Head]] · [[nanoGPT Architecture]] · [[PyTorch/model.parameters()|model.parameters()]] · [[PyTorch/torch.optim|torch.optim]]

## Вопросы для проверки

- Почему token id нельзя использовать как признак?
- Что хранится внутри `nn.Embedding`?
- Что реально делает `embedding(idx)`?
- Почему размер матрицы равен `(vocab_size, n_embd)`?
- Что изменяется во время обучения?
- Почему нельзя заменить Embedding обычной матрицей без потери интеграции с PyTorch?
- Зачем token embedding складывается с position embedding?
- Как token embedding matrix может использоваться на выходе модели?

## Следующие темы

- [[Position Embedding]]
- [[Weight Tying]]
- [[Статический и контекстный Embedding]]
- [[Query Key Value]]
