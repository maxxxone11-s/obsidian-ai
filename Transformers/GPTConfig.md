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
difficulty: easy
aliases:
  - GPT Configuration
  - Model Hyperparameters
---

# GPTConfig

Область: [[Transformers/Transformers|Transformers]]

## Академическое определение

GPTConfig — объект конфигурации, содержащий основные гиперпараметры архитектуры Transformer.

На его основе создаются все компоненты GPT-модели.

## Инженерное назначение

GPTConfig централизованно хранит параметры архитектуры, чтобы все слои создавались согласованно.

В nanoGPT-подобной реализации config передается в embedding layers, attention, MLP и [[Transformer Block]].

## Причина существования

Без единой конфигурации разные части модели могли бы ожидать разные размерности и стать несовместимыми друг с другом.

Например, embedding layer мог бы выдавать одну размерность, а attention block ожидал бы другую.

## Простое объяснение

GPTConfig — это чертеж модели.

Все остальные классы строятся по его параметрам.

## Как это работает

При создании каждого слоя ему передается объект `config`, из которого берутся нужные размеры и настройки.

Основные параметры:

- `block_size` — максимальная длина контекста.
- `vocab_size` — размер словаря токенов.
- `n_layer` — количество Transformer Block.
- `n_head` — количество attention heads.
- `n_embd` — размер embedding.
- `dropout` — вероятность Dropout.
- `bias` — использовать ли bias в Linear и LayerNorm.

## Пример

```text
config.n_layer = 12
config.n_head = 12
config.n_embd = 768
```

По этим значениям модель создает согласованные embedding, attention heads и список blocks.

## Типичные ошибки

- Путать гиперпараметры модели с обучаемыми весами.
- Считать GPTConfig частью обучения.
- Думать, что изменение config после создания модели автоматически перестраивает уже созданные слои.

## Связанные темы

[[nanoGPT Architecture]] · [[Transformer Block]] · [[Embedding Layer]] · [[Position Embedding]] · [[ModuleList]]

## Вопросы для проверки

- Какие параметры описывает GPTConfig?
- Какие параметры определяют архитектуру модели?
- Почему единая конфигурация защищает от несовместимых размерностей?

## Следующие темы

- GPT.__init__
- [[nanoGPT Architecture]]
- [[ModuleList]]
