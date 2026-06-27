---
type: system
tags:
  - system
---
# Правила агента для Obsidian Vault

Это Obsidian Vault для обучения **Python Backend** и **AI**.

## Основные правила

### Язык и форматирование
1. **Все заметки писать на русском языке**
2. **Использовать Markdown**
3. **Использовать Obsidian-ссылки** формата `[[Название темы]]`
4. **Не создавать дубликаты** заметок
5. **Перед созданием новой заметки** проверять, нет ли уже похожей

### YAML Frontmatter для учебных тем

Для каждой учебной темы использовать следующую структуру:

```yaml
---
type: concept
area: [область знания]
status: [статус]
created: [дата создания]
updated: [дата обновления]
tags: [теги]
---
```

### Возможные статусы

- **draft** — черновик
- **learning** — тема изучается
- **needs_review** — тема понята слабо
- **learned** — тема закреплена

## Структура Vault

```
Obsidian Vault
├── 00 Dashboard/
├── 01 Roadmap/
├── 02 Progress/
├── Python Backend/
├── Machine Learning/
├── Neural Networks/
├── PyTorch/
├── LangGraph/
├── RAG/
├── LLM Engineering/
├── AI Agents/
├── Algorithms/
├── Templates/
├── Indexes/
└── Inbox/
```

## Структура заметки

Каждая заметка должна содержать следующие секции:

```markdown
# Название темы

## Простое объяснение
Объясняем тему так, как если бы мы рассказывали другу.

## Зачем это нужно
Практическое применение и мотивация изучения.

## Как это работает
Детальное описание механизма работы.

## Пример
Практический код или пример использования.

## Типичные ошибки
Частые ошибки и как их избежать.

## Связанные темы
[[Тема 1]] · [[Тема 2]] · [[Тема 3]]
```

## Процесс добавления новой темы

После добавления темы необходимо обновить:

1. **Соответствующий Index файл** — добавить ссылку на новую тему
2. **02 Progress/Learning Log.md** — записать о добавлении темы
3. **01 Roadmap/Roadmap.md** — обновить дорожную карту обучения

## Validation Rules перед KNOWLEDGE_EXPORT

### Knowledge Areas

Knowledge Areas считаются стабильными доменами верхнего уровня.

Примеры:

- Python Backend
- Machine Learning
- Neural Networks
- PyTorch
- LangGraph
- RAG
- LLM Engineering
- AI Agents
- Algorithms & Data Structures

### Area Validation

Перед импортом любого **KNOWLEDGE_EXPORT** агент обязан:

1. Проверить, что `module.area` существует среди стабильных Knowledge Areas.
2. Никогда не создавать новую Knowledge Area автоматически.
3. Никогда не переименовывать существующую Knowledge Area автоматически.
4. Никогда не выбирать между похожими Knowledge Areas автоматически.
5. Если область неизвестна — остановить импорт и спросить пользователя.

Пример ответа:

```markdown
❌ Import stopped.

Unknown Knowledge Area:
Graph Theory

Possible actions:

- Create a new Knowledge Area
- Import into an existing Knowledge Area
- Cancel import
```

### Similar Area Detection

Если входящая область похожа на существующую, импорт нельзя продолжать автоматически.

Пример:

```yaml
Incoming:
area: Algorithms

Existing:
Algorithms & Data Structures
```

Агент обязан запросить подтверждение вместо предположения.

### Folder Creation

Папки внутри уже существующей и подтвержденной Knowledge Area можно создавать автоматически.

Пример:

```yaml
Existing area:
Algorithms & Data Structures

Incoming folder:
Algorithms/Graph Theory/DAG
```

Разрешено:

- создать `Graph Theory/`
- создать `DAG/`
- создать index-файлы
- создать concept-заметки

Это действие не требует дополнительного подтверждения пользователя.

### Automatic Import Rules

После подтверждения пользователем целевой Knowledge Area агент может:

- создавать папки
- создавать indexes
- создавать concept-заметки
- создавать backlinks
- обновлять Dashboard
- обновлять Knowledge Map
- обновлять Roadmap
- обновлять Learning Log

### Forbidden Operations

Агенту запрещено:

- создавать новые Knowledge Areas
- переименовывать существующие Knowledge Areas
- автоматически объединять Knowledge Areas
- переносить заметки между Knowledge Areas без подтверждения

### Alias Resolution

Aliases являются только подсказками.

Пример:

```yaml
Incoming:
Graph Theory

Possible destination:
Algorithms & Data Structures
```

Агент обязан спросить:

> Do you want to import this module into Algorithms & Data Structures?

Только после явного подтверждения импорт можно продолжать.

### Guiding Principle

Knowledge Areas верхнего уровня стабильны.

Внутренняя иерархия папок гибкая и может развиваться автоматически.

## Обязательные обновления после KNOWLEDGE_EXPORT

После каждого импорта **KNOWLEDGE_EXPORT** агент обязан автоматически обновить:

1. **00 Dashboard/Dashboard.md**
2. **00 Dashboard/Knowledge Map.md**
3. **01 Roadmap/Roadmap.md**
4. **02 Progress/Learning Log.md**
5. **Соответствующий файл в Indexes/**

### Правила обновления Dashboard

- Пересчитать все учебные концепции.
- Не считать служебные файлы:
  - `AGENTS.md`
  - `README.md`
  - `Templates/*`
  - `Indexes/*`
  - `00 Dashboard/*`
  - `01 Roadmap/*`
  - `02 Progress/*`
  - `Inbox/*`
- Считать только заметки с `type: concept`.
- Посчитать:
  - всего концепций
  - `status: learned`
  - `status: learning`
  - `status: needs_review`
  - `status: draft`
- Обновить таблицу **Статистика**.
- Обновить блок **Последние обновления**.
- Добавить дату импорта.
- Указать название импортированного модуля.

### Правила обновления Roadmap

- Если `KNOWLEDGE_EXPORT` содержит `module.name`, агент обязан обновить статус этого модуля.
- Если большинство ключевых `concepts` имеют `status: learned`, модуль считается пройденным.
- Если часть `concepts` имеет `needs_review`, модуль считается требующим повторения.
- Если большинство `concepts` имеют `draft` или `learning`, модуль считается в процессе.
- Roadmap нужно обновлять не только по отдельным концепциям, но и по модулю целиком: статус модуля, общий прогресс, завершение/активность следующего этапа и темы, требующие повторения.

### Правила обновления Knowledge Map

- Добавить новые `concepts` в соответствующий раздел `area`.
- Не дублировать ссылки.
- Сохранять удобный порядок.

### Правила обновления Learning Log

- Добавить запись с датой.
- Указать импортированный `module.name`.
- Перечислить новые и обновлённые `concepts`.
- Указать `weak_spots` из `learning_state`, если они есть.
- Указать `recommended_next_step`, если он есть.

## Работа с материалом из ChatGPT

Если пользователь вставляет материал из ChatGPT, нужно:

1. **Выделить главную тему**
2. **Понять связанные темы**
3. **Определить уровень понимания**
4. **Сохранить самое понятное объяснение**
5. **Добавить типичные ошибки** пользователя
6. **Создать связи между темами** через Obsidian-ссылки

### Классификация Algorithms & Data Structures

Если `KNOWLEDGE_EXPORT` или `SYNC_PACKAGE` относится к алгоритмам, структурам данных, LeetCode, графам, деревьям, DFS, BFS, сортировкам, хеш-таблицам, стеку, очереди, двум указателям, бинарному поиску или динамическому программированию — сохранять материал как:

```yaml
area: Algorithms & Data Structures
folder: Algorithms
tags:
  - algorithms
```

Для заметок этой области использовать YAML:

```yaml
area: Algorithms & Data Structures
tags:
  - algorithms
```

## Важные ограничения

- ✗ **Не удалять** существующие заметки без явного разрешения
- ⚠️ **Если нужна серьезная реструктуризация** Vault — сначала предложить план

## SYNC_PACKAGE Protocol

**SYNC_PACKAGE** — специальный протокол для обновления базы знаний структурированными пакетами данных из ChatGPT или других источников.

### Когда активировать

Если пользователь вставляет блок, начинающийся с:
```
SYNC_PACKAGE:
topic: ...
```

это означает структурированное обновление базы знаний.

### Обязательные действия агента

1. **Извлечь поля пакета:**
   - `topic` — название концепции
   - `area` — область знания
   - `status` — статус изучения
   - `confidence` — уровень уверенности (0-1)
   - `related` — связанные концепции
   - `summary` — краткое описание
   - `simple_explanation` — простое объяснение
   - `examples` — примеры кода
   - `common_mistakes` — типичные ошибки
   - `review_questions` — вопросы для проверки

2. **Создать или обновить основную заметку:**
   - Новая заметка: использовать [[Templates/Concept Template]]
   - Существующая заметка: аккуратно дополнить, не перезаписывать
   - Правильное размещение: `[area]/[topic].md`
   - YAML frontmatter обновить согласно пакету

3. **Создать stub-заметки для связанных концепций:**
   - Для каждой записи в `related`
   - Если заметка не существует
   - Со ссылками на основную концепцию

4. **Обновить Index файл:**
   - Добавить ссылку на новую концепцию
   - Обновить в соответствующем `Indexes/[area] Index.md`
   - Добавить описание или категорию

5. **Обновить учебные логи:**
   - `02 Progress/Learning Log.md` — записать о синхронизации
   - `01 Roadmap/Roadmap.md` — отметить прогресс по фазам
   - Обновить статистику заметок

6. **Правила сохранения данных:**
   - ✅ Сохранить всё новое содержимое
   - ✗ Не удалять существующий материал без разрешения
   - ⚠️ При конфликтах — предложить план действий

7. **Вывести отчет:**
   - Список всех созданных/обновленных файлов
   - Количество новых заметок
   - Новые связи между концепциями
   - Обновленную статистику

### Пример пакета

```
SYNC_PACKAGE:
topic: Gradient Descent
area: ml-basics
status: learned
confidence: 0.85
related: [Linear Regression, Optimization, Neural Networks, Learning Rate]
summary: Алгоритм оптимизации для нахождения минимума функции потерь
simple_explanation: Шаги вниз по склону функции к минимуму
examples:
  - Простой пример градиентного спуска для линейной регрессии
  - Пример с визуализацией шагов оптимизации
common_mistakes:
  - Неправильный выбор learning rate
  - Зависание в локальных минимумах
review_questions:
  - Что происходит при очень большом learning rate?
  - Как выбрать правильный learning rate?
```

### Совместимость с Knowledge Sync

SYNC_PACKAGE интегрируется с системой Knowledge Sync:
- Использует структуру из [[Templates/Sync Package.md]]
- Может быть преобразован в JSON при необходимости
- Совместим с автоматизацией в будущем

---

## Области знания (area)

Возможные значения для поля `area` в frontmatter:

- `Python Backend`
- `Machine Learning`
- `Neural Networks`
- `PyTorch`
- `LangGraph`
- `RAG`
- `LLM Engineering`
- `AI Agents`
- `Algorithms & Data Structures`

`folder` может быть внутренней структурой существующей области. Например, для `area: Algorithms & Data Structures` допустимы вложенные пути вроде `Algorithms/Graph Theory/DAG`.

---

**Дата создания:** 2026-06-26
**Версия:** 1.0
