---
type: template
tags:
  - template
  - system
name: "Sync Package Format"
version: "1.0"
created: 2026-06-26
updated: 2026-06-26
---

# 📦 Sync Package — Формат синхронизации знаний

## Описание

**Sync Package** — это формат данных, который используется для автоматического обновления базы знаний AI Second Brain из внешних источников (ChatGPT, других LLM и т.д.).

Текущий документ описывает структуру и формат пакета синхронизации **без реализации автоматизации**.

---

## Структура Sync Package

### JSON Schema

```json
{
  "sync_package": {
    "metadata": {
      "version": "1.0",
      "timestamp": "2026-06-26T12:00:00Z",
      "source": "chatgpt|claude|custom",
      "source_session_id": "unique-session-id",
      "user_id": "user-unique-id"
    },
    "concepts": [
      {
        "id": "concept-unique-id",
        "title": "Название концепции",
        "area": "backend|ml-basics|neural-networks|pytorch|rag|llm-engineering|ai-agents",
        "simple_explanation": "Простое объяснение...",
        "intuitive_explanation": "Интуитивное объяснение с аналогией...",
        "why_needed": "Зачем это нужно...",
        "examples": [
          {
            "title": "Простой пример",
            "code": "код здесь",
            "language": "python",
            "description": "описание"
          }
        ],
        "typical_errors": [
          {
            "error": "Название ошибки",
            "description": "Описание ошибки",
            "solution": "Как избежать",
            "example": "код неправильного примера"
          }
        ],
        "related_concepts": [
          "concept-id-1",
          "concept-id-2"
        ],
        "tags": ["тег1", "тег2"],
        "confidence_level": 0,
        "status": "draft|learning|needs_review|learned",
        "review_schedule": "immediate|1-day|3-days|7-days|14-days|30-days"
      }
    ],
    "updates": [
      {
        "concept_id": "concept-id",
        "action": "create|update|delete",
        "fields": {
          "field_name": "new_value"
        },
        "change_reason": "Причина изменения"
      }
    ],
    "relationships": [
      {
        "source_id": "concept-id-1",
        "target_id": "concept-id-2",
        "relation_type": "prerequisite|extends|related|contradicts"
      }
    ]
  }
}
```

---

## Поля и описания

### Metadata

| Поле | Тип | Обязательное | Описание |
|------|-----|-------------|---------|
| `version` | string | ✅ | Версия формата (1.0) |
| `timestamp` | ISO8601 | ✅ | Время создания пакета |
| `source` | enum | ✅ | Источник данных |
| `source_session_id` | string | ✅ | ID сессии источника |
| `user_id` | string | ✅ | ID пользователя |

### Concept

| Поле | Тип | Обязательное | Описание |
|------|-----|-------------|---------|
| `id` | string | ✅ | Уникальный идентификатор |
| `title` | string | ✅ | Название концепции |
| `area` | enum | ✅ | Область знания |
| `simple_explanation` | string | ✅ | Простое объяснение |
| `intuitive_explanation` | string | ✅ | Интуитивное объяснение |
| `why_needed` | string | ✅ | Практическое применение |
| `examples` | array | ✅ | Примеры кода |
| `typical_errors` | array | ✅ | Типичные ошибки |
| `related_concepts` | array | ❌ | ID связанных концепций |
| `tags` | array | ❌ | Теги для категоризации |
| `confidence_level` | number | ❌ | Уровень уверенности (0-100) |
| `status` | enum | ❌ | Статус изучения |
| `review_schedule` | enum | ❌ | График повторения |

### Example

| Поле | Тип | Описание |
|------|-----|---------|
| `title` | string | Название примера |
| `code` | string | Исходный код |
| `language` | string | Язык программирования |
| `description` | string | Описание примера |

### TypicalError

| Поле | Тип | Описание |
|------|-----|---------|
| `error` | string | Название ошибки |
| `description` | string | Полное описание |
| `solution` | string | Как избежать ошибки |
| `example` | string | Пример неправильного кода |

### Relationship

| Поле | Тип | Описание |
|------|-----|---------|
| `source_id` | string | ID исходной концепции |
| `target_id` | string | ID целевой концепции |
| `relation_type` | enum | Тип отношения |

---

## Области знания (area)

Допустимые значения:

- `python-basics` — Основы Python
- `backend` — Python Backend
- `databases` — Базы данных
- `ml-basics` — Основы ML
- `neural-networks` — Нейронные сети
- `pytorch` — PyTorch
- `rag` — RAG системы
- `llm-engineering` — LLM инженерия
- `ai-agents` — AI агенты

---

## Статусы

- `draft` — Черновик
- `learning` — Изучается
- `needs_review` — Требует повтора
- `learned` — Изучено

---

## График повторения

- `immediate` — Сейчас
- `1-day` — Через 1 день
- `3-days` — Через 3 дня
- `7-days` — Через 7 дней
- `14-days` — Через 14 дней
- `30-days` — Через 30 дней

---

## Типы отношений

| Тип | Описание |
|-----|---------|
| `prerequisite` | Предварительное знание |
| `extends` | Расширяет концепцию |
| `related` | Связана с концепцией |
| `contradicts` | Противоречит концепции |

---

## Примеры использования

### Пример 1: Создание новой концепции

```json
{
  "sync_package": {
    "metadata": {
      "version": "1.0",
      "timestamp": "2026-06-26T12:00:00Z",
      "source": "chatgpt",
      "source_session_id": "sess-123",
      "user_id": "user-456"
    },
    "concepts": [
      {
        "id": "async-await-01",
        "title": "Async/Await в Python",
        "area": "backend",
        "simple_explanation": "Механизм для написания асинхронного кода",
        "intuitive_explanation": "Как готовка обеда: вместо ожидания каждого блюда, вы готовите их параллельно",
        "why_needed": "Улучшает производительность I/O операций",
        "examples": [
          {
            "title": "Простой пример",
            "code": "async def hello():\n    await asyncio.sleep(1)",
            "language": "python",
            "description": "Базовая асинхронная функция"
          }
        ],
        "typical_errors": [
          {
            "error": "Забыли await",
            "description": "Функция вызвана без await",
            "solution": "Всегда используйте await перед корутинами",
            "example": "result = async_func()  # неправильно"
          }
        ],
        "tags": ["async", "concurrency"],
        "status": "draft"
      }
    ]
  }
}
```

---

## Будущие расширения

- [ ] Поддержка видео-ссылок
- [ ] Поддержка интерактивных примеров
- [ ] Поддержка quiz-вопросов
- [ ] Систем оценки сложности
- [ ] Версионирование концепций

---

**Версия:** 1.0
**Дата создания:** 2026-06-26
**Статус:** Готов к использованию
