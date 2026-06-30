---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: medium
difficulty: medium
aliases:
  - FFN
  - Position-wise Feed Forward
  - MLP
---

# Feed Forward Network

## Кратко

После Self-Attention каждый Transformer Block содержит обычную полносвязную нейронную сеть. Она применяется отдельно к каждому embedding.

## Простое объяснение

Attention отвечает на вопрос: "От кого взять информацию?"

Feed Forward отвечает: "Что означает собранная информация?"

## Зачем это нужно

После получения контекстной информации модель должна извлечь из нее новые признаки. Этим занимается Feed Forward Network.

## Как это работает

Типичная структура:

```text
Linear
  ↓
GELU или ReLU
  ↓
Linear
```

В отличие от Self-Attention, Feed Forward не взаимодействует с другими токенами. Он обрабатывает уже полученную информацию.

Обычно размерность сначала увеличивается:

```text
768 → 3072 → 768
```

Это позволяет сети строить более сложные признаки.

## Пример

```python
nn.Sequential(
    nn.Linear(768, 3072),
    nn.GELU(),
    nn.Linear(3072, 768),
)
```

## Типичные ошибки

- Путать Feed Forward с методом `forward()`.
- Считать Feed Forward частью Self-Attention.
- Считать Feed Forward механизмом общения между токенами.

## Вопросы для проверки

- Чем Feed Forward отличается от Self-Attention?
- Почему Feed Forward используется после Attention?

## Следующие темы

- [[LayerNorm]]

## Связанные темы

- [[Transformer Block]] · [[Residual Connection]] · [[PyTorch/nn.Linear|nn.Linear]]
