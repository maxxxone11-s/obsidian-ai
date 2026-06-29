---
type: dashboard
tags:
  - dashboard
  - system
created: 2026-06-26
updated: 2026-06-30
---

# 🗺️ Дорожная карта обучения

## Статус: ✅ Структура завершена, начинается наполнение контентом

## Фаза 0: Инфраструктура Vault ✅

- [x] Создана структура папок
- [x] Созданы правила (AGENTS.md)
- [x] Созданы шаблоны заметок
- [x] Установлена система SYNC_PACKAGE
- [x] Создано 37 stub концепций во всех доменах


## Аудит правил импорта KNOWLEDGE_EXPORT ✅

- [x] `AGENTS.md` требует обновлять Dashboard, Knowledge Map, Roadmap, Learning Log и соответствующий `Indexes/*` после каждого импорта.
- [x] Dashboard пересчитывается только по `type: concept` и без служебных файлов.
- [x] Roadmap обновляется по модулю целиком на основе `module.name` и статусов ключевых concepts.
- [x] Текущий vault синхронизирован после обновления правил.
- [x] Full Knowledge Synchronization выполнена: import-блоки удалены из concept-заметок, дубли canonical-секций объединены.

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

## Фаза 2: Machine Learning ✅ Fundamentals Completed

**Machine Learning Fundamentals пройден:**
- [[Что такое Machine Learning]], [[Dataset, Features и Labels]], [[Train Test Split]], [[Data Leakage]] ✅
- [[Regression]], [[Classification]], [[Linear Regression]], [[Logistic Regression]] ✅
- [[Loss Function]], [[Gradient Descent]], [[Feature Scaling]], [[Cross Validation]] ✅
- [[Accuracy Precision Recall и F1]], [[Confusion Matrix]] ✅
- [[Decision Tree]], [[Random Forest]], [[XGBoost]] ✅
- [[Связь Machine Learning и Deep Learning]] ✅
- [[Parameters и Hyperparameters]] 🔁 — единственная ключевая тема в needs_review

**Математическая база импортирована:**
- [[Machine Learning/Mathematics/README|Математика для Machine Learning]] ✅
- [[Вектор]], [[Матрица]], [[Матричное умножение]] ✅
- [[Производная]], [[Частная производная]], [[Градиент]] ✅
- [[Вероятность]], [[Entropy]] ✅
- [[Machine Learning/Mathematics/MSE|MSE]], [[Machine Learning/Mathematics/MAE|MAE]], [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] ✅

**Data Preparation после рефакторинга:**
- [[Feature Scaling]] превращён в overview ✅
- [[Normalization]], [[Standardization]], [[Fit Transform и Data Leakage]] ✅
- [[Scaling и Gradient Descent]], [[Scaling для KNN и SVM]], [[Scaling и Tree-Based Models]] ✅

**Прогресс модуля:** 22/23 ключевых тем learned, 1 тема needs_review.
**Статус:** Machine Learning Fundamentals пройден. Следующий практический шаг после PyTorch: pandas → sklearn → train/test split → Logistic Regression → Decision Tree → Random Forest → XGBoost.

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

**Модуль PyTorch — Tensor Fundamentals импортирован:**
- [[PyTorch/Tensor|Tensor]] ✅ — основной объект PyTorch
- [[PyTorch/Tensors/Tensor Dimensions (ndim)|Tensor Dimensions (ndim)]] ✅ — количество осей
- [[PyTorch/Shape|Tensor Shape]] ✅ — структура Tensor
- [[PyTorch/Tensors/Tensor Creation|Tensor Creation]] ✅ — создание Tensor
- [[PyTorch/Tensors/Tensor Dtype|Tensor Dtype]] ✅ — типы данных
- [[PyTorch/Reshape|Reshape]], [[PyTorch/View|View]], [[PyTorch/Unsqueeze|Unsqueeze]], [[PyTorch/Squeeze|Squeeze]] ✅ — изменение формы
- [[PyTorch/Tensors/Tensor Indexing and Slicing|Tensor Indexing and Slicing]] 🔁 — требует повторения
- [[PyTorch/Broadcasting|Broadcasting]] 🔁 — требует повторения

**Прогресс модуля:** 6/8 ключевых тем learned, 2 темы needs_review.
**Статус:** Tensor Fundamentals почти пройден; перед переходом к [[PyTorch/Autograd|Autograd]] повторить [[PyTorch/Broadcasting|Broadcasting]] и shape после slicing.

**Следующий активный блок:**
- [[PyTorch/Tensors/Tensor Operations|Tensor Operations]]
- [[PyTorch/Autograd|Autograd]]
- [[PyTorch/Dataset|Dataset]] и [[PyTorch/DataLoader|DataLoader]]
- [[PyTorch/nn.Module|nn.Module]]

**PyTorch Foundations II синхронизирован:**
- [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch (matmul)]] ✅ — различие `*` и `@`
- [[PyTorch/nn.Linear|nn.Linear]] ✅ — Linear Layer как `x @ w + b`
- [[PyTorch/Autograd|Autograd]] ✅ — computation graph и `backward()`
- [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]] ✅ — `model(x) → loss → zero_grad → backward → step`
- [[Machine Learning/Mathematics/Производная|Производная]] 🔁 — повторить правила производных и смысл изменения входа

**Прогресс модуля Foundations II:** 6/7 ключевых тем learned, 1 тема needs_review.

**PyTorch Foundations III синхронизирован:**
- [[Neural Networks/Train Validation Test|Train Validation Test]] ✅ — роли train, validation и test
- [[PyTorch/nn.Module|nn.Module]] ✅ — `__init__`, `forward` и вызов `model(x)`
- [[PyTorch/Многослойная нейронная сеть|Многослойная нейронная сеть]] ✅ — слои строят новые признаки последовательно
- [[Neural Networks/ReLU|ReLU]] ✅ — нелинейность между Linear-слоями
- [[PyTorch/Анализ архитектуры модели по слоям|Анализ архитектуры модели по слоям]] ✅ — чтение shape по слоям
- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] ✅ и [[PyTorch/model.eval()|model.eval()]] ✅ — режимы модели
- [[Neural Networks/Output|Output]] ✅ и [[PyTorch/nn.Linear|nn.Linear]] ✅ — последний слой определяется задачей
- [[PyTorch/Чтение архитектуры PyTorch-проектов|Чтение архитектуры PyTorch-проектов]] ✅ — базовое чтение архитектур

**Прогресс модуля Foundations III:** 8/8 ключевых тем learned.
**Требует повторения:** выбор последнего слоя для разных типов классификации, связь последнего слоя и loss function, анализ реальных GitHub-проектов.

**Цель:** увидеть в коде цепочку [[Neural Networks/Forward Pass|Forward Pass]] → [[Neural Networks/Loss|Loss]] → [[Neural Networks/Backpropagation|Backpropagation]] → [[Neural Networks/Gradient|Gradient]] → [[Neural Networks/Optimizer|Optimizer]]

## Фаза 5: LangGraph ✅

**Синхронизация LangGraph завершена:**
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
**Последнее обновление:** 2026-06-30
**Статус:** Структурный фундамент готов ✅

## Фаза Algorithms: Graph Theory ✅

**Модуль Graph Theory Foundations I синхронизирован:**
- [[Algorithms/Graph Theory/Basics/Что такое граф|Что такое граф]] ✅
- [[Algorithms/Graph Theory/Basics/Вершины и ребра|Вершины и ребра]] ✅
- [[Algorithms/Graph Theory/Basics/Изолированная вершина|Изолированная вершина]] ✅
- [[Algorithms/Graph Theory/Basics/Удаление вершины и удаление ребра|Удаление вершины и удаление ребра]] ✅
- [[Algorithms/Graph Theory/Basics/Ориентированный и неориентированный граф|Ориентированный и неориентированный граф]] ✅
- [[Algorithms/Graph Theory/Basics/Путь|Путь]] ✅
- [[Algorithms/Graph Theory/Trees/Дерево|Дерево]] ✅
- [[Algorithms/Graph Theory/Trees/Root Parent Child Leaf|Root Parent Child Leaf]] ✅
- [[Algorithms/Graph Theory/Basics/Цикл|Цикл]] ✅
- [[Algorithms/Graph Theory/DAG/DAG|DAG]] ✅
- [[Algorithms/Graph Theory/Basics/Список смежности|Список смежности]] ✅

**Прогресс модуля:** 11/11 ключевых тем learned.
**Требует повторения:** строгое определение дерева, альтернативные способы хранения графов и Big O для графовых операций.
**Следующий шаг:** изучить матрицу смежности и сравнить ее со списком смежности.

## Фаза Algorithms: Python — Рекурсия ✅

**Модуль Python — Рекурсия импортирован:**
- [[Algorithms/Recursion/Basics/Recursion|Recursion]] ✅ — идея уменьшения задачи
- [[Algorithms/Recursion/Basics/Base Case|Base Case]] ✅ — остановка рекурсии
- [[Algorithms/Recursion/Internals/Call Stack|Call Stack]] ✅ — stack frame и размотка
- [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]] ✅ — рекурсия через `return`
- [[Algorithms/Recursion/Examples/Factorial|Factorial]] ✅ — классический пример
- [[Algorithms/Recursion/Examples/Рекурсивная сумма чисел|Рекурсивная сумма чисел]] ✅
- [[Algorithms/Recursion/Examples/Рекурсивный разворот строки|Рекурсивный разворот строки]] ✅
- [[Algorithms/Recursion/Examples/Рекурсивная проверка палиндрома|Рекурсивная проверка палиндрома]] ✅
- [[Algorithms/Recursion/Examples/String Slicing in Recursion|String Slicing in Recursion]] 🔁 — повторить срезы

**Прогресс модуля:** 8/9 ключевых тем learned, 1 тема needs_review.
**Статус:** базовая рекурсия пройдена; следующий активный блок — [[Algorithms/Recursion/Trees/Tree Traversal|Tree Traversal]], [[Algorithms/DFS|DFS]] и рекурсия на графах.
**Требует повторения:** срезы строк, различие «вызов» и «возврат», рекурсия на деревьях и графах.

## Фаза Algorithms: Рекурсия на деревьях ✅

**Модуль Рекурсия на деревьях. DFS и рекурсивные вычисления синхронизирован:**
- [[Algorithms/Recursion/Trees/Дерево как рекурсивная структура данных|Дерево как рекурсивная структура данных]] ✅
- [[Algorithms/Recursion/Trees/DFS на дереве|DFS на дереве]] ✅
- [[Algorithms/Recursion/Trees/Рекурсия с возвратом результата из поддерева|Рекурсия с возвратом результата из поддерева]] ✅
- [[Algorithms/Recursion/Trees/Подсчет количества узлов дерева|Подсчет количества узлов дерева]] ✅
- [[Algorithms/Recursion/Trees/Поиск максимальной глубины дерева|Поиск максимальной глубины дерева]] ✅

**Прогресс модуля:** 5/5 ключевых тем learned.
**Требует повторения:** объединение результатов нескольких рекурсивных вызовов, выбор между суммой и максимумом, не смешивать цикл и генератор.
