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
  - torch.nn.functional
  - Functional API
---

# Module и Functional в PyTorch

## Кратко

В PyTorch вычисления и хранение параметров часто разделены: `nn.Module` хранит состояние, а функции из `torch.nn.functional` выполняют математику.

## Простое объяснение

Module хранит параметры. Functional выполняет математику.

## Зачем это нужно

Такое разделение делает библиотеку более гибкой и позволяет повторно использовать вычислительные функции.

## Как это работает

Класс `nn.Module` хранит состояние модели:

- веса;
- bias;
- гиперпараметры.

Например, `nn.MultiheadAttention` содержит:

- `in_proj_weight`;
- `in_proj_bias`;
- `num_heads`.

Затем module вызывает functional-реализацию и передает ей нужные параметры.

## Пример

```text
MultiheadAttention.forward()
    ↓
F.multi_head_attention_forward()
```

Похожий паттерн:

```text
nn.ReLU()
    ↓
F.relu()
```

## Типичные ошибки

- Считать Functional отдельным слоем.
- Путать хранение параметров и вычисления.

## Вопросы для проверки

- Что хранит Module?
- Что делает Functional?
- Почему PyTorch разделяет эти обязанности?

## Следующие темы

- [[MultiheadAttention в PyTorch]]

## Связанные темы

- [[PyTorch/nn.Module|nn.Module]] · [[MultiheadAttention в PyTorch]] · [[Query Key Value]]
