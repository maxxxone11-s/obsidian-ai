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

## Фаза 3: Neural Networks ✅ Completed

**Модуль завершён:**
- [[Dataset]], [[Train Set]], [[Validation|Validation Set]], [[Test Set]] ✅ — data pipeline
- [[Feature]], [[Weights]], [[Bias]], [[Perceptron]], [[Model]] ✅ — фундамент нейрона и модели
- [[Score]], [[Activation Function]], [[Sigmoid]], [[Tanh]], [[ReLU]], [[Leaky ReLU]], [[Softmax]] ✅ — функции активации
- [[Forward Pass]], [[Loss]], [[Backpropagation]], [[Gradient]], [[Machine Learning/Gradient Descent|Gradient Descent]], [[Learning Rate]] ✅ — базовый цикл обучения
- [[Optimizer]], [[Batch Gradient Descent]], [[SGD]], [[Mini-Batch Gradient Descent]], [[Momentum]], [[Adam]] ✅ — оптимизаторы
- [[Batch]], [[Epoch]] ✅ — организация обучения
- [[Overfitting]], [[Dropout]], [[Batch Normalization]] ✅ — регуляризация
- [[Inference]], [[model.train() и model.eval()]], [[torch.no_grad()]] ✅ — inference и PyTorch-preview
- [[Chain Rule]] 🔁, [[Adam]] 🔁, [[Batch Normalization]] vs [[Machine Learning/Feature Scaling|Feature Scaling]] 🔁 — зоны повторения

**Статус:** Completed. Следующий активный модуль — [[PyTorch/Index|PyTorch]]

## Фаза 4: PyTorch 🚀 Active

**Следующий активный модуль:**
- [[Tensor]] — данные и параметры
- [[nn.Module]] — реализация модели и Forward Pass
- [[Autograd]] — автоматические градиенты
- [[torch.optim]] — оптимизаторы и optimizer.step()
- [[model.eval()]] — режим Inference

**Цель:** увидеть в коде цепочку [[Forward Pass]] → [[Loss]] → [[Backpropagation]] → [[Gradient]] → [[Optimizer]]

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
