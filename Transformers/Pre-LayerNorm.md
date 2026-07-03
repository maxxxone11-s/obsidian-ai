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
  - Pre-LN
  - Pre LayerNorm
---

# Pre-LayerNorm

## Академическое определение

Pre-LayerNorm — вариант архитектуры Transformer Block, в котором [[LayerNorm]] применяется до Attention и MLP, а не после [[Residual Connection]].

## Инженерное назначение

Pre-LayerNorm повышает стабильность обучения глубоких Transformer.

В современных GPT-подобных LLM этот порядок часто используется, чтобы облегчить масштабирование на большое количество блоков.

## Причина существования

Архитектура Post-LN хуже масштабируется на большое количество Transformer Block.

Pre-LN помогает стабилизировать входы модулей до вычисления Attention или MLP.

## Простое объяснение

Сначала нормализуем embedding, затем вычисляем Attention или MLP, затем добавляем результат через Residual.

## Как это работает

Порядок выполнения:

```text
LayerNorm -> Module -> Residual
```

Для Attention:

```python
x = x + self.attn(self.ln_1(x))
```

## Пример

```text
Post-LN:
x = ln(x + attn(x))

Pre-LN:
x = x + attn(ln(x))
```

## Типичные ошибки

- Считать, что все Transformer используют одинаковый порядок операций.
- Путать Pre-LN и Post-LN.
- Считать, что LayerNorm всегда стоит после Residual.

## Связанные темы

[[LayerNorm]] · [[Residual Connection]] · [[Transformer Block]] · [[nanoGPT Architecture]]

## Вопросы для проверки

- Почему современные GPT используют Pre-LN?
- Чем Pre-LN отличается от Post-LN?

## Следующие темы

- GPT Block
- [[nanoGPT Architecture]]
