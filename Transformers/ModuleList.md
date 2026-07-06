---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-07-06
updated: 2026-07-06
tags:
  - transformers
confidence: high
difficulty: medium
aliases:
  - nn.ModuleList
  - Module List
---

# ModuleList

## Академическое определение

ModuleList — специальный контейнер PyTorch для хранения списка обучаемых модулей.

В Transformer он часто используется для списка независимых [[Transformer Block]].

## Инженерное назначение

ModuleList регистрирует все Transformer Block как части модели.

Благодаря этому PyTorch видит вложенные модули и включает их параметры в жизненный цикл модели.

## Причина существования

Обычный список Python не сообщает PyTorch о существовании вложенных модулей.

Если хранить blocks в обычном `list`, PyTorch может не включить их в `model.parameters()`, `state_dict()`, `train()`, `eval()` и `model.to(device)`.

## Простое объяснение

ModuleList похож на обычный список, но понимает, что внутри находятся нейронные слои.

Это список, который PyTorch умеет регистрировать.

## Как это работает

Каждый [[Transformer Block]] создается как отдельный объект и помещается в ModuleList.

PyTorch автоматически отслеживает все вложенные модули:

- добавляет их параметры в `model.parameters()`;
- сохраняет их в `state_dict`;
- переключает их через `train()` и `eval()`;
- переносит их через `model.to(device)`.

## Пример

```python
nn.ModuleList([
    Block(config),
    Block(config),
    Block(config),
])
```

Каждый вызов `Block(config)` создает новый block со своими параметрами.

## Типичные ошибки

- Использовать обычный `list` вместо ModuleList.
- Считать ModuleList самостоятельным слоем.
- Думать, что ModuleList сам выполняет forward pass.
- Путать одинаковую архитектуру blocks с общими весами.

## Связанные темы

[[Transformer Block]] · [[nanoGPT Architecture]] · [[PyTorch/nn.Module|nn.Module]] · [[PyTorch/model.parameters()|model.parameters()]] · [[GPTConfig]]

## Вопросы для проверки

- Почему нельзя использовать обычный список?
- Что автоматически делает ModuleList?
- Почему ModuleList не является самостоятельным вычислительным слоем?

## Следующие темы

- Block Iteration
- [[Transformer Block]]
- [[nn.Module __call__]]
