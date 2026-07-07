---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-07
updated: 2026-07-07
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Self-Attention Forward Pass
  - Attention Execution Pipeline
  - CausalSelfAttention
---

# CausalSelfAttention.forward Pipeline

## Академическое определение

`CausalSelfAttention.forward` — метод, который последовательно преобразует входной Tensor в выход Self-Attention через QKV-проекцию, вычисление внимания, объединение голов и выходную проекцию.

## Инженерное назначение

Этот pipeline реализует полный алгоритм Multi-Head Self-Attention как последовательность операций над Tensor.

В nanoGPT-подобном коде он показывает, как теория attention превращается в конкретный forward pass.

## Причина существования

Разделение вычислений на последовательные этапы делает реализацию модульной, понятной и оптимизированной.

Без такого pipeline Attention выглядел бы как одна непрозрачная операция, хотя внутри него есть несколько разных задач: проекция, изменение формы, scores, mask, softmax, weighted sum и output projection.

## Простое объяснение

Один embedding проходит через цепочку преобразований и возвращается обратно в том же размере, но уже содержит информацию о других токенах.

## Как это работает

Последовательность операций:

```text
x
    ↓
c_attn
    ↓
split(Q, K, V)
    ↓
split heads
    ↓
QK^T
    ↓
scaling
    ↓
causal mask
    ↓
softmax
    ↓
dropout
    ↓
@ V
    ↓
concat heads
    ↓
c_proj
    ↓
resid_dropout
```

Вход и выход имеют одинаковую внешнюю форму:

```text
(B, T, C) -> (B, T, C)
```

## Пример

```text
Вход:
(B, T, C)

Выход:
(B, T, C)
```

Размерность возвращается к `C`, потому что attention block должен быть совместим с [[Residual Connection]] и следующим [[Transformer Block]].

## Типичные ошибки

- Воспринимать Attention как одну операцию.
- Не понимать порядок вычислений внутри forward.
- Смешивать уровни `GPT.forward`, `Block.forward` и `CausalSelfAttention.forward`.
- Смотреть на отдельные строки кода без удержания общего контекста метода.

## Связанные темы

[[Self-Attention Pipeline]] · [[Attention Tensor Shapes]] · [[Multi-Head Attention]] · [[Attention Scores]] · [[Causal Mask]] · [[Transformer Block]]

## Вопросы для проверки

- Какие этапы проходит Tensor внутри Self-Attention?
- Почему размерность входа и выхода одинакова?
- Где в pipeline появляются heads?
- Где применяется `c_proj`?

## Следующие темы

- Flash Attention
- [[Attention Tensor Shapes]]
- [[MultiheadAttention в PyTorch]]
