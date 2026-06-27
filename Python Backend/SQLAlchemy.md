---
type: concept
area: Python Backend
status: draft
created: 2026-06-26
updated: 2026-06-27
tags:
  - python-backend
  - sqlalchemy
  - orm
  - database
confidence: 0
---

# SQLAlchemy

ORM (Object-Relational Mapping) фреймворк для Python.

## Простое объяснение

SQLAlchemy позволяет работать с БД через Python объекты вместо написания SQL вручную.

## Интуитивное объяснение

Как переводчик между языками — SQLAlchemy переводит операции с объектами в SQL запросы.

## Зачем это нужно

- Абстракция над SQL
- Меньше ошибок SQL injection
- Переносимость между СУБД
- Более чистый код

## Как это работает

### Основные компоненты
- Models (модели)
- Sessions (сессии)
- Relationships (связи)
- Query API

## Пример

```python
from sqlalchemy import Column, Integer, String
from sqlalchemy.ext.declarative import declarative_base

Base = declarative_base()

class User(Base):
    __tablename__ = "users"
    id = Column(Integer, primary_key=True)
    name = Column(String)
```

## Типичные ошибки

- Неправильно настроенные отношения
- Забывают делать commit()
- Lazy loading вместо eager loading

## Связанные темы

- [[SQL]] — под капотом SQLAlchemy используется SQL
- [[PostgreSQL]] — одна из поддерживаемых БД
- [[Alembic]] — для миграций схемы
