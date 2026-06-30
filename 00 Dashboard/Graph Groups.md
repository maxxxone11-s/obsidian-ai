---
type: dashboard
tags:
  - dashboard
  - system
created: 2026-06-26
updated: 2026-06-30
---

# Graph Groups

Инструкция для ручной настройки визуальных групп в Obsidian Graph View.

## Как настроить

1. Открой Graph View.
2. Перейди в Settings.
3. Открой Groups.
4. Добавь группы ниже и назначь им цвета.

## Группы

- `tag:#python-backend` — синий
- `tag:#machine-learning` — зелёный
- `tag:#neural-networks` — оранжевый
- `tag:#transformers` — сине-фиолетовый
- `tag:#pytorch` — фиолетовый
- `tag:#langgraph` — красный
- `tag:#rag` — бирюзовый
- `tag:#llm-engineering` — жёлтый
- `tag:#ai-agents` — розовый
- `tag:#algorithms` — голубой

## Как скрыть служебные файлы

Чтобы скрыть служебные файлы в Graph View, в поиске Graph View используй фильтр:

```text
-tag:#system
```

Если нужно видеть только учебные заметки:

```text
-tag:#system -tag:#template -tag:#index
```

Фильтр для чистого учебного графа без служебных и практических заметок:

```text
-tag:#system -tag:#practice
```
