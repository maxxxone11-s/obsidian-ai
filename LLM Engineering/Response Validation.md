---
type: concept
area: LLM Engineering
knowledge_area: LLM Engineering
status: learned
created: 2026-07-10
updated: 2026-07-11
tags: [llm-engineering, structured-output, validation]
confidence: high
difficulty: easy
aliases: [Response Validation, LLM Response Validation, Structured Output Validation, Валидация ответа LLM]
---

# Response Validation

Область: [[LLM Engineering/LLM Engineering|LLM Engineering]]

## Академическое определение

Response Validation — процесс проверки того, что ответ LLM соответствует ожидаемой структуре и типам данных перед использованием приложением.

## Инженерное назначение

Response Validation предотвращает попадание некорректно структурированных данных модели в бизнес-логику и создаёт контролируемую точку для обработки ошибок.

## Причина существования

Даже при использовании Structured Output приложение не должно слепо доверять внешнему ответу. Нарушение schema или типов способно вызвать исключение либо ошибочное поведение downstream-компонентов.

## Простое объяснение

Проверка убеждается, что LLM вернула данные нужной формы, например `age` действительно является `int`. Она проверяет структуру, а не истинность смысла.

## Как это работает

1. Приложение задаёт ожидаемую schema.
2. Ответ LLM парсится в структурированные данные.
3. Pydantic или другой validator проверяет поля, типы и обязательные ограничения.
4. Валидный объект передаётся бизнес-логике.
5. Ошибка направляется в [[LLM Engineering/Error Recovery|Error Recovery]].

## Пример

```python
from pydantic import BaseModel

class Person(BaseModel):
    age: int
```

Если модель возвращает значение `age`, несовместимое с `int`, validation завершается ошибкой до вызова бизнес-логики.

## Типичные ошибки

- Путать Response Validation с проверкой фактической истинности ответа.
- Путать структурную validation с бизнес-валидацией.
- Использовать данные модели до проверки schema.
- Игнорировать обработку validation errors.

## Связанные темы

[[LLM Engineering/Structured Output|Structured Output]] · [[LLM Engineering/Pydantic в Structured Output|Pydantic в Structured Output]] · [[LLM Engineering/JSON Schema|JSON Schema]] · [[LLM Engineering/Error Recovery|Error Recovery]]

## Вопросы для проверки

- Что именно проверяет Response Validation?
- Чем структурная validation отличается от бизнес-логики?
- Почему Structured Output не отменяет проверку ответа?

## Следующие темы

[[LLM Engineering/Error Recovery|Error Recovery]]
