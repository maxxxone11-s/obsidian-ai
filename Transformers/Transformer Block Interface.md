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
  - Transformer Block Interface
---

# Transformer Block Interface

## Академическое определение

Transformer Block Interface — контракт, по которому [[Transformer Block]] является самостоятельным модулем с фиксированным входом и выходом.

Он принимает embedding и возвращает embedding той же формы.

## Инженерное назначение

Интерфейс блока изолирует внутреннюю реализацию Transformer Block от остальной архитектуры модели.

`GPT.forward()` может вызывать `x = block(x)`, не зная деталей LayerNorm, Attention, MLP и Residual внутри блока.

## Причина существования

Фиксированный интерфейс позволяет изменять внутреннюю реализацию блока без изменения внешнего кода модели.

Это делает архитектуру модульной и поддерживаемой.

## Простое объяснение

GPT знает только одно: Block принимает embedding и возвращает embedding той же формы.

Что именно происходит внутри — ответственность самого Block.

## Как это работает

Block инкапсулирует:

- [[LayerNorm]]
- [[Multi-Head Attention]]
- [[Feed Forward Network]]
- [[Residual Connection]]

Снаружи это выглядит как простой вызов:

```python
x = block(x)
```

## Пример

```python
for block in self.transformer.h:
    x = block(x)
```

Каждый `block` может быть отдельным объектом с собственными параметрами, но интерфейс остается одинаковым.

## Типичные ошибки

- Считать, что `GPT.forward()` знает внутреннюю реализацию Block.
- Путать одинаковый интерфейс с одинаковыми параметрами.

## Связанные темы

[[Transformer Block]] · [[nanoGPT Architecture]] · [[nn.Module __call__]] · [[PyTorch/nn.Module|nn.Module]]

## Вопросы для проверки

- Почему `GPT.forward()` не зависит от внутреннего устройства Block?
- Почему важно, что Block возвращает embedding той же формы?

## Следующие темы

- Attention Module
- [[nn.Module __call__]]
