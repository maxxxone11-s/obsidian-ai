---
type: dashboard
tags:
  - dashboard
  - system
created: 2026-06-26
updated: 2026-06-26
---

# 🗺️ Дорожная карта обучения

## Статус: ✅ Структура завершена, начинается наполнение контентом

## Фаза 0: Инфраструктура Vault ✅

- [x] Создана структура папок
- [x] Созданы правила (AGENTS.md)
- [x] Созданы шаблоны заметок
- [x] Установлена система SYNC_PACKAGE
- [x] Создано 37 stub концепций во всех доменах

## Фаза 1: Основы Python Backend 📋

**Структура создана (12 концепций):**
- [[Python Core]] — основы Python
- [[OOP]] — объектно-ориентированное программирование
- [[Asyncio]] — асинхронное программирование
- [[FastAPI]] — веб-фреймворк
- [[SQL]] — язык БД
- [[SQLAlchemy]] — ORM
- [[Alembic]] — миграции БД
- [[PostgreSQL]] — реляционная БД
- [[Redis]] — кеш и очереди
- [[Docker]] — контейнеризация
- [[Git]] — версионный контроль
- [[Linux]] — операционная система

**Статус:** Все в статусе draft, ожидают наполнения контентом

## Фаза 2: Machine Learning 📋

**Структура создана (12 концепций):**
- [[Feature Scaling]] ✅ — **ЗАВЕРШЕНО (confidence: 80%)**
- [[Normalization]] — stub
- [[Standardization]] — stub
- [[Gradient Descent]] — stub
- [[KNN]] — stub
- [[SVM]] — stub
- [[Linear Regression]] — stub
- [[Logistic Regression]] — stub
- [[Loss Function]] — stub
- [[Train Test Split]] — stub
- [[Overfitting]] — stub
- [[Underfitting]] — stub

**Статус:** 1 тема завершена, остальные в draft

## Фаза 3: Neural Networks 📋

**Структура создана (5 концепций):**
- [[Perceptron]] — stub
- [[Weights]] — stub
- [[Bias]] — stub
- [[Activation Function]] — stub
- [[Backpropagation]] — stub

**Статус:** Все в статусе draft

## Фаза 4: PyTorch 📋

**Структура создана (8 концепций):**
- [[Tensor]] — stub
- [[Shape]] — stub
- [[Broadcasting]] — stub
- [[View]] — stub
- [[Reshape]] — stub
- [[Unsqueeze]] — stub
- [[Squeeze]] — stub
- [[Autograd]] — stub

**Статус:** Все в статусе draft

## Фаза 5: LangGraph ✅

**Импорт KNOWLEDGE_EXPORT завершён:**
- [[LangGraph Overview]] ✅ — overview агентных графов
- [[Agent Loop]] ✅ — базовый цикл агента
- [[State]] ✅ — центральный объект графа
- [[State Update]] ✅ — возврат изменений из Node
- [[Node]] ✅ — отдельный шаг выполнения
- [[Edge]] ✅ и [[Conditional Edge]] ✅ — маршрутизация графа
- [[Router]] ✅ — выбор следующего пути
- [[StateGraph]] ✅ — сборка структуры графа
- [[START, END и invoke()]] ✅ — запуск и завершение графа
- [[Checkpoint и Memory]] ✅ — состояние процесса и память
- [[Human-in-the-loop]] ✅ — interrupt/resume
- [[Tool Node]] ✅ и [[LLM Tool Calling]] ✅ — инструменты агента
- [[Planner и Executor]] ✅ — планирование и выполнение
- [[Multi-Agent, Supervisor и Subgraph]] ✅ — production-паттерны
- [[Production Architecture]] ✅ — архитектура крупных AI-систем

**Практика:** создано 7 мини-проектов LangGraph.

**Статус:** теория импортирована, следующий шаг — пройти практику без LLM API

## Фаза 6: AI Engineering 📋

**Структура создана (5 концепций):**
- [[RAG]] — stub
- [[Embeddings]] — stub
- [[Vector Database]] — stub
- [[LLM]] — stub
- [[AI Agent]] — stub

**Статус:** Все в статусе draft

---

## Следующие шаги

1. **Наполнение контентом** — преобразование draft в полноценные концепции
2. **SYNC_PACKAGE примеры** — использование протокола для обновления с ChatGPT
3. **Проверка и проработка** — переход из draft в learning/learned
4. **Интеграция примеров** — добавление кода и практических примеров

---

**Дата создания:** 2026-06-26
**Последнее обновление:** 2026-06-26
**Статус:** Структурный фундамент готов ✅
