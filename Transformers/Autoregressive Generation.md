---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-04
updated: 2026-07-04
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - Next Token Prediction
  - Autoregressive Decoding
  - Autoregressive Generation
---

# Autoregressive Generation

## Академическое определение

Autoregressive Generation — способ генерации, при котором модель предсказывает следующий токен на основе уже существующего контекста, добавляет его к последовательности и повторяет процесс.

## Инженерное назначение

Этот механизм обеспечивает согласованность генерации с постоянно изменяющимся контекстом.

В decoder-only LLM он связывает [[Language Modeling Head]], sampling и [[KV Cache]] в практический inference loop.

## Причина существования

Будущие токены зависят от предыдущих предсказаний.

Их невозможно корректно предсказать заранее независимо друг от друга, потому что каждый новый токен изменяет весь последующий контекст и влияет на дальнейшие вычисления attention.

## Простое объяснение

Модель пишет текст по одному токену.

После каждого нового токена она заново учитывает текущий контекст и выбирает следующий.

## Как это работает

```text
context
    ↓
Transformer
    ↓
logits следующего токена
    ↓
sampling
    ↓
новый token
    ↓
context + token
    ↓
повторить
```

Новый токен добавляется к последовательности, после чего снова выполняются embedding, attention, MLP и вычисление новых logits.

При использовании [[KV Cache]] часть вычислений для прошлых токенов переиспользуется.

## Пример

Контекст:

```text
Я люблю
```

может привести к одному распределению следующего токена.

Контекст:

```text
Я люблю изучать
```

уже приводит к другому распределению вероятностей.

## Типичные ошибки

- Считать возможным независимое предсказание нескольких следующих токенов.
- Забывать, что каждый новый токен изменяет attention всей последовательности.
- Путать autoregressive generation с параллельным обучением на полной последовательности.
- Не связывать generation loop с [[Causal Mask]].

## Связанные темы

[[Causal Mask]] · [[Language Modeling Head]] · [[Temperature Sampling]] · [[KV Cache]] · [[Attention Complexity During Inference]] · [[Neural Networks/Logits|Logits]]

## Вопросы для проверки

- Почему невозможно надежно предсказать сразу несколько будущих токенов независимо?
- Что изменяется после генерации каждого нового токена?
- Как Causal Mask связана с autoregressive generation?
- Зачем KV Cache нужен во время генерации?

## Следующие темы

- [[KV Cache]]
- [[Temperature Sampling]]
- Inference Pipeline
