---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-01
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - Skip Connection
  - Residual Link
  - Identity Connection
---

# Residual Connection

## Академическое определение

Residual Connection — архитектурная связь, при которой выход некоторого преобразования `F(x)` складывается с исходным входом `x`.

В Transformer это обычно записывается как:

```text
y = x + F(x)
```

где `F(x)` может быть результатом Attention или FeedForward.

## Инженерное назначение

Residual Connection сохраняет исходное представление токена и добавляет к нему новую информацию, полученную внутри текущего [[Transformer Block]].

В инженерной архитектуре Transformer эта связь помогает передавать информацию через много блоков без полного переписывания embedding на каждом шаге.

## Причина существования

Если каждый блок полностью заменял бы embedding, модель могла бы быстро терять уже полезную информацию.

Residual Connection позволяет каждому блоку уточнять представление постепенно: не "стереть и записать заново", а "добавить полезное изменение".

## Простое объяснение

Attention не переписывает embedding. Он добавляет к нему новую информацию.

## Как это работает

Для Attention:

```text
y = x + Attention(x)
```

Если:

```text
x = [2, 5]
Attention(x) = [1, -2]
```

то:

```text
Output = [2, 5] + [1, -2] = [3, 3]
```

После суммы обычно применяется [[LayerNorm]]:

```text
x + Attention(x)
    ↓
LayerNorm
```

Нормализуется уже итоговое представление, которое будет передано следующему Transformer Block.

## Пример

Вместо:

```python
x = attention(x)
```

используется:

```python
x = x + attention(x)
x = layer_norm(x)
```

## Типичные ошибки

- Считать, что Attention полностью заменяет embedding.
- Считать Residual Connection механизмом обучения.
- Путать Residual Connection с Backpropagation.
- Считать порядок `Residual → LayerNorm` случайным.

## Связанные темы

[[Transformer Block]] · [[LayerNorm]] · [[Feed Forward Network]] · [[Постепенное уточнение embedding]]

## Вопросы для проверки

- Почему нельзя просто заменить embedding результатом Attention?
- Что сохраняет Residual Connection?
- Почему глубокие Transformer используют Residual?
- Почему после суммы часто применяется LayerNorm?

## Следующие темы

- [[LayerNorm]]
- [[Постепенное уточнение embedding]]
