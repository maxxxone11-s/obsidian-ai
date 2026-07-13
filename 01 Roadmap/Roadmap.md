---
type: dashboard
tags:
  - dashboard
  - system
created: 2026-06-26
updated: 2026-07-13
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
- [[Machine Learning/Normalization|Normalization]], [[Machine Learning/Feature Standardization|Standardization]], [[Fit Transform и Data Leakage]] ✅
- [[Scaling и Gradient Descent]], [[Scaling для KNN и SVM]], [[Scaling и Tree-Based Models]] ✅

**Прогресс модуля:** 22/23 ключевых тем learned, 1 тема needs_review.
**Статус:** Machine Learning Fundamentals пройден. Следующий практический шаг после PyTorch: pandas → sklearn → train/test split → Logistic Regression → Decision Tree → Random Forest → XGBoost.

## Фаза 2.5: Statistics ✅

**Модуль Statistics Foundations for Machine Learning синхронизирован в отдельную область [[Statistics/Index|Statistics]]:**
- [[Statistics/Mean|Mean]] ✅ — центр данных
- [[Statistics/Variance|Variance]] ✅ — разброс вокруг среднего
- [[Statistics/Причина использования квадратов в статистике|Причина использования квадратов в статистике]] ✅ — усиление больших ошибок
- [[Statistics/Standard Deviation|Standard Deviation]] ✅ — разброс в исходных единицах
- [[Statistics/Min-Max Normalization|Min-Max Normalization]] ✅ — scaling к диапазону 0..1
- [[Statistics/Z-score Standardization|Standardization]] ✅ — mean 0 и standard deviation 1
- [[Statistics/Z-score|Z-score]] ✅ — расстояние от среднего в единицах standard deviation
- [[Statistics/Normal Distribution|Normal Distribution]] ✅ — normal distribution и правило 68-95-99.7
- [[Statistics/Связь основных статистических понятий|Связь основных статистических понятий]] ✅ — связка Mean → Variance → Std → Z-score

**Прогресс модуля:** 9/9 ключевых тем learned.
**Formula Update:** добавлены формулы для [[Statistics/Mean|Mean]], [[Statistics/Variance|Variance]], [[Statistics/Standard Deviation|Standard Deviation]], [[Statistics/Min-Max Normalization|Min-Max Normalization]], [[Statistics/Z-score Standardization|Standardization]], [[Statistics/Z-score|Z-score]] и [[Statistics/Normal Distribution|Normal Distribution]].
**Требует повторения:** различие между Standardization и Normalization в терминологии, интерпретация Standard Deviation как возврата к исходным единицам измерения.
**Следующий шаг:** изучить поиск выбросов с помощью Z-score и статистическую подготовку данных в NumPy, pandas и scikit-learn.

## Фаза 3: Neural Networks ✅ Completed

**Модуль завершён:**
- [[Neural Networks/Dataset для обучения модели|Dataset]], [[Train Set]], [[Neural Networks/Validation Set|Validation Set]], [[Test Set]] ✅ — data pipeline
- [[Feature]], [[Weights]], [[Bias]], [[Perceptron]], [[Model]] ✅ — фундамент нейрона и модели
- [[Score]], [[Activation Function]], [[Sigmoid]], [[Tanh]], [[ReLU]], [[Leaky ReLU]], [[Softmax]] ✅ — функции активации
- [[Forward Pass]], [[Loss]], [[Backpropagation]], [[Gradient]], [[Machine Learning/Gradient Descent|Gradient Descent]], [[Learning Rate]] ✅ — базовый цикл обучения
- [[Optimizer]], [[Batch Gradient Descent]], [[SGD]], [[Mini-Batch Gradient Descent]], [[Momentum]], [[Adam]] ✅ — оптимизаторы
- [[Batch]], [[Epoch]] ✅ — организация обучения
- [[Machine Learning/Overfitting|Overfitting]], [[Dropout]], [[Batch Normalization]] ✅ — регуляризация
- [[Inference]], [[model.train() и model.eval()]], [[torch.no_grad()]] ✅ — inference и PyTorch-preview
- [[Chain Rule]] 🔁, [[Adam]] 🔁, [[Batch Normalization]] vs [[Machine Learning/Feature Scaling|Feature Scaling]] 🔁 — зоны повторения

**Статус:** Completed. Следующий активный модуль — [[PyTorch/Index|PyTorch]]

## Фаза 3.5: Transformers 🚀 Active

**Модуль Transformer Foundations I синхронизирован в отдельную область [[Transformers/Index|Transformers]]:**
- [[Transformers/Embedding Layer|Embedding Layer]] ✅ — обучаемая таблица признаков
- [[Transformers/Статический и контекстный Embedding|Статический и контекстный Embedding]] ✅ — переход от статического представления к контекстному
- [[Transformers/Query Key Value|Query Key Value]] ✅ — три линейных преобразования embedding
- [[Transformers/Attention Scores|Attention Scores]] ✅ — матрица похожести `QK^T`
- [[Transformers/Attention Weights|Attention Weights]] ✅ — нормализация scores через [[Neural Networks/Softmax|Softmax]]
- [[Transformers/Attention Output|Attention Output]] ✅ — weighted sum по Value
- [[Transformers/Embedding Space|Embedding Space]] 🔁 — геометрическая интерпретация требует повторения
- [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]] ✅ — packed projection и `in_proj_weight`

**Прогресс модуля Transformer Foundations I:** 7/8 ключевых тем learned, 1 тема needs_review.
**Требует повторения:** геометрическая интерпретация embedding space, интуиция изменения embedding после каждого слоя, связь Scores → Softmax → Weighted Sum и постепенное уточнение embedding в нескольких Transformer Block.
**Следующий шаг:** изучить полный Transformer Block: Residual Connection, LayerNorm, FeedForward и ручную реализацию SelfAttention на PyTorch.

**Модуль Transformer Foundations II синхронизирован:**
- [[Transformers/Transformer Block|Transformer Block]] ✅ — базовая строительная единица Transformer
- [[Transformers/Residual Connection|Residual Connection]] ✅ — сохранение исходного embedding через `x + attention(x)`
- [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]] ✅ — итеративное уточнение представлений
- [[Transformers/Feed Forward Network|Feed Forward Network]] ✅ — обработка собранной контекстной информации
- [[Transformers/Module и Functional в PyTorch|Module и Functional в PyTorch]] ✅ — разделение хранения параметров и вычислений
- [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]] ✅ — packed QKV через `in_proj_weight`
- [[Transformers/Batch Matrix Multiplication|Batch Matrix Multiplication]] ✅ — пакетное вычисление attention scores
- [[Transformers/LayerNorm|LayerNorm]] 🔁 — требует статистической базы

**Прогресс модуля Transformer Foundations II:** 7/8 ключевых тем learned, 1 тема needs_review.
**Требует повторения:** математическая природа LayerNorm, статистический смысл нормализации и полный цикл вычислений внутри LayerNorm.
**Следующий шаг:** изучить Mean, Variance, Standard Deviation, Normalization и Z-score, затем вернуться к LayerNorm и полной реализации Transformer Block.

**Модуль Transformer Foundations III синхронизирован:**
- [[Transformers/LayerNorm|LayerNorm]] ✅ — стандартизация embedding внутри Transformer Block
- [[Transformers/Residual Connection|Residual Connection]] ✅ — порядок `x + F(x) → LayerNorm`
- [[Transformers/Feed Forward Network|Feed Forward Network]] ✅ — FeedForward как position-wise MLP

**Прогресс модуля Transformer Foundations III:** 3/3 ключевых тем learned.
**Требует повторения:** различия между Post-LN и Pre-LN архитектурами, внутренняя реализация LayerNorm в PyTorch, практическое влияние `γ` и `β` во время обучения.
**Следующий шаг:** изучить Multi-Head Attention, различия Single Head и Multi-Head Attention, затем анализировать полный Transformer Block в современных LLM.

**Модуль Transformer Foundations IV синхронизирован:**
- [[Transformers/Multi-Head Attention|Multi-Head Attention]] ✅ — несколько независимых attention heads
- [[Transformers/Query Key Value|Query Key Value]] ✅ — head projection через разные `Wq`, `Wk`, `Wv`
- [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]] ✅ — tensor reshaping, output projection и реализация heads
- [[Transformers/Batch Matrix Multiplication|Batch Matrix Multiplication]] ✅ — объединение `batch × heads` для `torch.bmm`

**Прогресс модуля Transformer Foundations IV:** 4/4 ключевых тем learned.
**Требует повторения:** полная реализация `multi_head_attention_forward()`, Attention Mask, Padding Mask и Decoder Self-Attention.
**Следующий шаг:** разобрать исходный код `multi_head_attention_forward()`, изучить Causal Mask и перейти к различиям Encoder и Decoder.

**Transformers generation module синхронизирован:**
- [[Transformers/KV Cache|KV Cache]] ✅ — кэширование Key и Value во время autoregressive generation
- [[Transformers/Attention Complexity During Inference|Attention Complexity During Inference]] ✅ — почему длинный контекст остается дорогим
- [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]] ✅ — между блоками передаются embedding, а не Q/K/V
- [[Transformers/Language Modeling Head|Language Modeling Head]] ✅ — преобразование final embedding в logits словаря
- [[Transformers/Temperature Sampling|Temperature Sampling]] ✅ — управление разнообразием генерации
- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]] ✅ — разделение памяти приложения и cache одного ответа
- [[Transformers/nanoGPT Architecture|nanoGPT Architecture]] ✅ — структура GPT как набор модулей

**Прогресс модуля Transformers generation:** 7/7 ключевых тем learned.
**Требует повторения:** различие между памятью приложения и KV Cache, создание независимых экземпляров классов в цикле Python, практическое чтение исходного кода nanoGPT.
**Следующий шаг:** полностью разобрать `GPT.forward()` из nanoGPT строка за строкой и сопоставить каждую инструкцию с архитектурными компонентами.

**Transformer architecture module синхронизирован:**
- [[Transformers/Position Embedding|Position Embedding]] ✅ — отдельная таблица признаков позиций
- [[Transformers/Embedding Layer|Embedding Layer]] ✅ — token embedding + position embedding
- [[Transformers/Residual Connection|Residual Connection]] ✅ — философия постепенного улучшения представления
- [[Transformers/Pre-LayerNorm|Pre-LayerNorm]] ✅ — порядок LayerNorm → Module → Residual
- [[Transformers/Transformer Block Interface|Transformer Block Interface]] ✅ — Block как стабильный интерфейс `embedding -> embedding`
- [[Transformers/nn.Module __call__|nn.Module __call__]] ✅ — почему `block(x)` запускает PyTorch module
- [[Transformers/Query Key Value|Query Key Value]] ✅ — combined QKV projection через `c_attn`
- [[Transformers/Self-Attention Pipeline|Self-Attention Pipeline]] ✅ — полная цепочка QKV → scores → weights → output
- [[Transformers/Multi-Head Attention|Multi-Head Attention]] ✅ — роль output projection `c_proj`

**Прогресс модуля Transformer architecture:** 9/9 ключевых тем learned.
**Требует повторения:** перестановка размерностей `transpose`, матричное умножение по последним двум осям и shape тензоров на каждом этапе.
**Следующий шаг:** разобрать оставшуюся реализацию `CausalSelfAttention.forward()` до конца, включая scaling, causal mask и final output projection в nanoGPT.

**Transformers module синхронизирован:**
- [[Transformers/Causal Mask|Causal Mask]] ✅ — честное параллельное обучение decoder через запрет будущих токенов
- [[Transformers/Attention Scores|Attention Scores]] ✅ — scaling через `sqrt(head_dim)` перед Softmax
- [[Transformers/Query Key Value|Query Key Value]] ✅ — семантическое разделение поиска, релевантности и передачи информации
- [[Transformers/Веса как долговременная память модели|Веса как долговременная память модели]] ✅ — знания модели находятся в параметрах, а не во временных embedding
- [[Transformers/Разделение ролей LLM и RAG|Разделение ролей LLM и RAG]] ✅ — LLM рассуждает, RAG приносит внешний контекст
- [[Transformers/Weight Tying|Weight Tying]] ✅ — общая матрица Token Embedding и LM Head
- [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]] ✅ — Transformer как последовательность переходов между пространствами представлений
- [[Transformers/Autoregressive Generation|Autoregressive Generation]] ✅ — генерация по одному токену с обновлением контекста

**Прогресс модуля Transformers:** 8/8 ключевых тем learned.
**Требует повторения:** связь матричного умножения, Softmax и Linear с архитектурной логикой; геометрия embedding space; почему Linear лучше прямого поиска ближайшего embedding.
**Следующий шаг:** перейти к механизму обучения Transformer: Teacher Forcing, Cross Entropy Loss, Backpropagation и обновление весов.

**Transformers nanoGPT Source Code синхронизирован:**
- [[Transformers/GPTConfig|GPTConfig]] ✅ — config как чертёж архитектуры модели
- [[Transformers/Embedding Layer|Embedding Layer]] ✅ — `nn.Embedding` как обучаемая lookup-таблица и PyTorch module
- [[Transformers/Position Embedding|Position Embedding]] ✅ — WPE как отдельная таблица позиций
- [[Transformers/nanoGPT Architecture|nanoGPT Architecture]] ✅ — `wte`, `wpe`, `drop`, `h`, `ln_f` и параметры config
- [[Transformers/ModuleList|ModuleList]] ✅ — контейнер для регистрации списка Transformer Block
- [[Transformers/Transformer Block|Transformer Block]] ✅ — одинаковая архитектура blocks, но независимые веса
- [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]] ✅ — независимые blocks изучают разные уровни представления

**Прогресс модуля Transformers nanoGPT Source Code:** 7/7 ключевых тем learned.
**Требует повторения:** отличие `nn.Embedding` от Tensor, чтение PyTorch-кода без подсказок и жизненный цикл `nn.Module` внутри модели.
**Следующий шаг:** продолжить разбор `GPT.forward()` через ModuleList и выполнение каждого Transformer Block.

**Transformers nanoGPT Source Code II синхронизирован:**
- [[Transformers/CausalSelfAttention.forward Pipeline|CausalSelfAttention.forward Pipeline]] ✅ — полный порядок операций внутри `CausalSelfAttention.forward`
- [[Transformers/Attention Tensor Shapes|Attention Tensor Shapes]] ✅ — изменение shape Tensor на этапах Self-Attention
- [[Transformers/Self-Attention Pipeline|Self-Attention Pipeline]] ✅ — связь теории attention с source-code pipeline
- [[Transformers/Attention Scores|Attention Scores]] ✅ — raw scores `q @ k^T` до Softmax
- [[Transformers/Multi-Head Attention|Multi-Head Attention]] ✅ — роль `c_proj` после concat heads
- [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]] ✅ — `split heads`, `transpose`, `view/reshape` как операции формы
- [[Transformers/Feed Forward Network|Feed Forward Network]] ✅ — expansion `n_embd -> 4 × n_embd -> GELU -> n_embd`
- [[Transformers/Transformer Block|Transformer Block]] ✅ — различие задач Attention и FeedForward

**Прогресс модуля Transformers nanoGPT Source Code II:** 8/8 ключевых тем learned.
**Требует повторения:** математический смысл `QK^T`, самостоятельное восстановление pipeline и чтение исходного кода Transformer.
**Следующий шаг:** завершить модуль Transformer на текущем уровне и перейти к LLM Engineering, RAG и AI Agents.

## Фаза 3.5: LLM Engineering ✅ Foundation Completed

**План модуля создан:** [[LLM Engineering/Plan|LLM Engineering Plan]]

**Цель:** научиться строить production-подобные приложения поверх LLM API: prompts, structured output, function calling, streaming, context engineering, cost optimization и production patterns.

**Learning Path:**
- Основы LLM API ✅
- Prompt Engineering ✅
- Structured Output ✅
- Function Calling ✅
- Streaming ✅
- Context Engineering ✅
- Cost Optimization ✅
- Production Patterns ⏳
- Работа с несколькими провайдерами ⏳
- Финальный production-подобный сервис ⏳

**Статус:** фундамент LLM Engineering пройден; расширенные production patterns остаются в roadmap для последующего углубления.

**LLM Engineering API Integration синхронизирован:**
- [[LLM Engineering/OpenRouter через OpenAI SDK|OpenRouter через OpenAI SDK]] ✅ — OpenAI-compatible API через `base_url`
- [[LLM Engineering/Архитектура OpenAI SDK|Архитектура OpenAI SDK]] ✅ — структура SDK как дерево resources
- [[LLM Engineering/Цепочка выполнения chat.completions.create|Цепочка выполнения chat.completions.create]] ✅ — request lifecycle от Python method до HTTP/JSON response
- [[LLM Engineering/Messages как источник контекста модели|Messages как источник контекста модели]] ✅ — messages как полный контекст запроса
- [[Transformers/Temperature Sampling|Temperature Sampling]] ✅ — temperature как API parameter для управления случайностью
- [[LLM Engineering/Top-p (Nucleus Sampling)|Top-p (Nucleus Sampling)]] ✅ — nucleus sampling как ограничение множества кандидатов

**Прогресс блока Основы LLM API:** 6 ключевых тем learned, блок в процессе.
**Требует повторения:** отсутствует.
**Следующий шаг:** изучить `max_tokens` и `stop`, затем перейти к Prompt Engineering.

**LLM Engineering Prompt Engineering & Structured Output синхронизирован:**
- [[LLM Engineering/Max Tokens|Max Tokens]] ✅ — ограничение длины ответа, стоимости и latency
- [[LLM Engineering/Stop Sequence|Stop Sequence]] ✅ — остановка генерации по маркеру
- [[LLM Engineering/Prompt Engineering|Prompt Engineering]] ✅ — проектирование входного контекста
- [[LLM Engineering/System Prompt|System Prompt]] ✅ — постоянные правила поведения модели
- [[LLM Engineering/User Prompt|User Prompt]] ✅ — runtime context текущего запроса
- [[LLM Engineering/Prompt Templates|Prompt Templates]] ✅ — шаблоны prompts с подстановкой данных
- [[LLM Engineering/Few-shot Prompting|Few-shot Prompting]] ✅ — in-context examples без обучения модели
- [[LLM Engineering/Delimiters|Delimiters]] ✅ — явные границы блоков prompt
- [[LLM Engineering/Output Formatting|Output Formatting]] ✅ — контракт формата ответа
- [[LLM Engineering/Structured Output|Structured Output]] ✅ — API-механизм структурированного ответа
- [[LLM Engineering/JSON Schema|JSON Schema]] ✅ — контракт структуры JSON
- [[LLM Engineering/Pydantic в Structured Output|Pydantic в Structured Output]] ✅ — single source of truth для структуры
- [[LLM Engineering/Response Validation|Validation]] ✅ — проверка структуры ответа
- [[LLM Engineering/Error Recovery|Error Recovery]] ✅ — восстановление после ошибок generation/validation

**Прогресс LLM Engineering:** блоки “Основы LLM API”, “Prompt Engineering” и “Structured Output” имеют изученные ключевые темы.
**Требует повторения:** отсутствует.

**LLM Engineering Function Calling & Streaming синхронизирован:**
- [[LLM Engineering/Function Calling|Function Calling]] ✅ — модель формирует запрос, backend выполняет функцию
- [[LLM Engineering/Function Schema|Function Schema]] ✅ — контракт инструмента для модели
- [[LLM Engineering/Tool Selection|Tool Selection]] ✅ — семантический выбор инструмента
- [[LLM Engineering/Tool Loop|Tool Loop]] ✅ — управляемый backend цикл вызова и возврата результата
- [[LLM Engineering/Multiple Tool Calls|Multiple Tool Calls]] ✅ — несколько вызовов и выбор стратегии выполнения
- [[LLM Engineering/Tool Calling|Tool Calling]] ✅ — обобщённый интерфейс внешних возможностей
- [[LLM Engineering/Streaming|Streaming]] ✅ — постепенная передача ответа
- [[LLM Engineering/Streaming API в OpenAI SDK|Streaming API в OpenAI SDK]] ✅ — итератор chunks и `delta.content`
- [[LLM Engineering/Streaming при Function Calling|Streaming при Function Calling]] ✅ — сборка потоковых tool calls

**Прогресс LLM Engineering:** изучены ключевые темы блоков “Основы LLM API”, “Prompt Engineering”, “Structured Output”, “Function Calling” и “Streaming”; модуль остаётся в процессе.

**LLM Engineering Context Window & Memory Management синхронизирован:**
- [[LLM Engineering/Context Window|Context Window]] ✅ — общий бюджет входных и выходных токенов
- [[LLM Engineering/Переполнение Context Window|Переполнение Context Window]] ✅ — обнаружение и сокращение слишком большого запроса
- [[LLM Engineering/Token Counting|Token Counting]] ✅ — контроль лимита и стоимости в токенах
- [[LLM Engineering/Conversation Memory|Conversation Memory]] ✅ — история хранится и передаётся backend
- [[LLM Engineering/Conversation State|Conversation State]] ✅ — полное состояние текущего диалога
- [[LLM Engineering/Memory Management|Memory Management]] ✅ — отбор релевантного контекста

**Требует практического повторения:** расчёт токенов для сложных запросов, production-реализация Summary и Sliding Window.
**Прогресс LLM Engineering:** изучены ключевые темы блоков от “Основы LLM API” до “Context Engineering”; модуль остаётся в процессе.

**LLM Engineering Cost Optimization & Production Architecture синхронизирован:**
- [[LLM Engineering/Стоимость LLM-запросов|Стоимость LLM-запросов]] ✅ — input/output tokens и тарифы модели
- [[LLM Engineering/Cost Optimization|Cost Optimization]] ✅ — системное снижение стоимости без потери качества
- [[LLM Engineering/Исключение ненужных вызовов LLM|Исключение ненужных вызовов LLM]] ✅ — обработка простых задач backend-кодом
- [[LLM Engineering/Model Routing|Model Routing]] ✅ — выбор минимально достаточной модели
- [[LLM Engineering/Prompt Caching|Prompt Caching]] ✅ — повторное использование стабильного prompt-префикса
- [[LLM Engineering/Production Pipeline LLM-приложения|Production Pipeline LLM-приложения]] ✅ — LLM как один из сервисов backend

**Статус LLM Engineering:** Foundation Completed. Ключевые основы API, prompts, structured output, tools, streaming, context management, cost optimization и production pipeline изучены.
**Требует практического повторения:** Semantic Cache, сложный Model Router и мониторинг стоимости.
**Следующий шаг:** перейти к [[RAG/Index|RAG]], используя знания о Context Window, Memory Management, Tool Calling и Production Pipeline.

## Фаза 3.6: RAG 🚧 In progress

**План модуля создан:** [[RAG/Plan|RAG Plan]]

**Цель:** научиться проектировать, реализовывать и оценивать production-подобные RAG-системы от ingestion и embeddings до retrieval, generation, evaluation и monitoring.

**Learning Path:**

- Почему появился RAG 🚧
- Embeddings 🚧
- Chunking 🚧
- Vector Database 🚧
- Retrieval 🚧
- Hybrid Search 🚧
- Reranking 🚧
- Generation 🚧
- Evaluation ✅
- Production RAG 🚧
- Advanced RAG ⏳
- Финальный проект ⏳

**RAG Retrieval Pipeline синхронизирован:**

- [[AI Engineering/RAG|Retrieval-Augmented Generation (RAG)]] ✅ — внешний retrieval перед генерацией
- [[AI Engineering/Embeddings|Embedding]] ✅ — семантическое векторное представление
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]] ✅ — сравнение направлений embeddings
- [[RAG/Chunk|Chunk]] ✅ — смысловая единица индексирования и поиска
- [[RAG/Fixed-size Chunking|Fixed-size Chunking]] ✅ — простой baseline разбиения
- [[RAG/Chunk Overlap|Chunk Overlap]] ✅ — сохранение контекста на границах
- [[RAG/Recursive Chunking|Recursive Chunking]] ✅ — иерархическое разбиение по естественным границам
- [[RAG/Semantic Chunking]] ✅ — разбиение по изменениям смысла между соседними фрагментами

**RAG Retrieval Pipeline II синхронизирован:**

- [[RAG/Retrieval|Retrieval]] ✅ — быстрый отбор релевантных chunks
- [[RAG/Top-K Retrieval|Top-K Retrieval]] ✅ — ограничение числа кандидатов
- [[RAG/Reranking|Reranking]] ✅ — точная повторная оценка найденных документов
- [[RAG/Hybrid Search|Hybrid Search]] ✅ — объединение semantic и keyword search
- [[RAG/Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion (RRF)]] ✅ — объединение ранжированных списков без сравнения несовместимых raw scores

**Production RAG Pipeline начат:**

- [[AI Engineering/Vector Database|Vector Database]] 🚧 — хранение готовых embeddings и поиск chunks по query embedding
- [[RAG/Document Loader|Document Loader]] ✅ — извлечение текста из внешнего источника
- [[RAG/Indexing Pipeline|Indexing Pipeline]] ✅ — предварительная подготовка и сохранение индекса документов
- [[RAG/Query Pipeline|Query Pipeline]] ✅ — online retrieval, reranking и generation для каждого вопроса
- [[RAG/Orchestrator|Orchestrator]] ✅ — управление порядком вызова независимых компонентов
- [[RAG/Query Transformation|Query Transformation]] ✅ — улучшение поискового запроса до построения embedding
- [[RAG/Query Rewrite|Query Rewrite]] ✅ — формирование самостоятельного вопроса с учётом истории
- [[RAG/Query Expansion|Query Expansion]] ✅ — дополнение запроса связанными терминами
- [[RAG/HyDE|HyDE]] ✅ — retrieval по embedding гипотетического документа
- [[RAG/Multi Query Retrieval|Multi Query Retrieval]] ✅ — несколько независимых поисков с fusion результатов
- [[RAG/Step-back Prompting|Step-back Prompting]] ✅ — переход от частного вопроса к фундаментальной концепции
- [[RAG/Prompt Construction|Prompt Construction]] ✅ — сборка system instructions, context и user question
- [[RAG/Context Construction|Context Construction]] ✅ — дедупликация, объединение и ограничение retrieved chunks
- [[RAG/Lost in the Middle|Lost in the Middle]] ✅ — влияние позиции информации в длинном prompt
- [[RAG/Ingestion Pipeline|Ingestion Pipeline]] ✅ — полный document processing lifecycle
- [[RAG/SearchResult|SearchResult]] ✅ — контракт между retriever, reranker и context builder
- [[RAG/Production RAG Pipeline|Production RAG Pipeline]] ✅ — независимые компоненты и orchestration полного lifecycle

**RAG Evaluation синхронизирован:**

- [[RAG/Evaluation|Evaluation]] ✅ — количественное сравнение изменений RAG
- [[RAG/Ground Truth|Ground Truth]] ✅ — эталон релевантных документов
- [[Machine Learning/Accuracy Precision Recall и F1|Precision и Recall]] ✅ — чистота и полнота retrieval
- [[RAG/Mean Reciprocal Rank (MRR)|Mean Reciprocal Rank (MRR)]] ✅ — позиция первого релевантного документа
- [[RAG/Hit Rate|Hit Rate]] ✅ — наличие хотя бы одного релевантного документа в Top-K
- [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]] ✅ — качество всего ранжированного списка

**RAG Generation Evaluation синхронизирован:**

- [[RAG/Faithfulness|Faithfulness]] ✅ — подтверждение claims переданным контекстом
- [[RAG/Answer Relevancy|Answer Relevancy]] ✅ — соответствие ответа вопросу
- [[RAG/Context Precision|Context Precision]] ✅ — чистота итогового контекста
- [[RAG/Context Recall|Context Recall]] ✅ — полнота информации для ответа
- [[RAG/LLM-as-a-Judge|LLM-as-a-Judge]] ✅ — автоматизированная оценка сложных свойств ответа

**Статус:** `learning`; Evaluation, Query Transformation и базовая Production Architecture изучены, практическая интеграция реальных компонентов продолжается.
**Предварительные знания:** [[LLM Engineering/Index|LLM Engineering]], [[Transformers/Index|Transformers]], [[Machine Learning/Index|Machine Learning]], [[Python Backend/Index|Python Backend]], [[AI Agents/Index|AI Agents]].
**Требует повторения:** чтение полной RAG-архитектуры в коде, реальная Embedding Model и различия Document, SearchResult и VectorRecord.
**Следующий шаг:** интегрировать реальную Embedding Model и собрать Production RAG Pipeline с настоящим API.

## Фаза 3.7: Vector Databases 🚀 Active

**План модуля:** [[Vector Databases/Plan|Vector Databases Plan]]

**Цель:** научиться проектировать и эксплуатировать vector search: от геометрии embeddings и ANN-индексов до pgvector, Qdrant, Pinecone и production lifecycle.

**Learning Path:**

- Основы векторного поиска ⏳
- Similarity Search ✅ — [[Vector Databases/Exact Search|Exact Search]], [[Vector Databases/Approximate Nearest Neighbor (ANN)|ANN]] и [[Vector Databases/Recall в Approximate Nearest Neighbor|ANN Recall]]
- HNSW и IVF 🔄 — изучены [[Vector Databases/HNSW|HNSW]], [[Vector Databases/Greedy Search в HNSW|Greedy Search]], [[Vector Databases/Local Maximum в HNSW|Local Maximum]] и [[Vector Databases/Hierarchical Levels в HNSW|Hierarchical Levels]]; параметры и IVF впереди
- pgvector ⏳
- Qdrant ⏳
- Pinecone ⏳
- Производительность ⏳
- RAG Integration ⏳
- Production ⏳
- Практика ⏳

**Связанные знания:** [[AI Engineering/Vector Database|Vector Database]], [[AI Engineering/Embeddings|Embedding]], [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]], [[RAG/Retrieval|Retrieval]].

**Статус:** `learning`; изучены Exact Search, ANN, ANN Recall и базовая графовая архитектура HNSW. Модуль остаётся активным, поскольку параметры HNSW, IVF, конкретные Vector Databases и production-практика ещё впереди.

**Требует повторения:** Entry Point, параллельное исследование нескольких кандидатов, параметры `M`, `efConstruction`, `efSearch` и вероятностное распределение узлов по уровням.

**Следующий шаг:** изучить `M`, `efConstruction` и `efSearch`, затем реализовать небольшой HNSW-подобный граф на Python и визуализировать компромисс Recall/скорость.

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
- [[PyTorch/PyTorch Dataset|Dataset]] и [[PyTorch/DataLoader|DataLoader]]
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

**PyTorch Foundations — GitHub Projects & ML Architecture синхронизирован:**
- [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]] ✅ — порядок чтения ML-репозитория
- [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]] ✅ — структура проекта
- [[PyTorch/model.py как отдельная ответственность|model.py как отдельная ответственность]] ✅ — файл модели
- [[PyTorch/train.py как центр обучения|train.py как центр обучения]] ✅ — центр обучения
- [[PyTorch/config.py|config.py]] ✅ — настройки проекта
- [[PyTorch/PyTorch Dataset|Dataset]] ✅ и [[PyTorch/DataLoader|DataLoader]] ✅ — данные и batch-интерфейс
- [[PyTorch/Separation of Concerns|Separation of Concerns]] ✅ — разделение ответственности
- [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]] ✅ — контракт передачи данных
- [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]] 🔁 — гиперпараметры vs параметры датасета

**Прогресс модуля GitHub Projects & ML Architecture:** 8/9 ключевых тем learned, 1 тема needs_review.
**Требует повторения:** чтение крупных репозиториев без подсказок, анализ архитектуры до реализации, интуиция выбора `hidden_size`.

**PyTorch Foundations — Loss, Optimization & Autograd синхронизирован:**
- [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]] ✅ — loss для multi-class classification
- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] ✅ — математическая идея loss
- [[Neural Networks/Logits|Logits]] ✅ — сырые outputs модели
- [[Neural Networks/Adam|Adam]] ✅ — адаптивный optimizer
- [[PyTorch/model.parameters()|model.parameters()]] ✅ — trainable параметры
- [[PyTorch/Autograd|Autograd]] ✅ — computation graph и `backward()`
- [[Neural Networks/torch.no_grad()|torch.no_grad()]] ✅ — inference без graph
- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] ✅ и [[PyTorch/model.eval()|model.eval()]] ✅ — режимы модели
- [[PyTorch/DataLoader|DataLoader]] ✅ — batch loading под капотом

**Прогресс модуля Loss, Optimization & Autograd:** 9/9 ключевых тем learned.
**Требует повторения:** внутреннее устройство Adam, математическая основа CrossEntropyLoss, хранение промежуточных значений в computation graph, DataLoader на уровне реализации.

**PyTorch Foundations — GitHub File Analysis & Inference Pipeline синхронизирован:**
- [[PyTorch/model.py как отдельная ответственность|model.py как отдельная ответственность]] ✅ — review файла модели
- [[PyTorch/train.py как центр обучения|train.py как центр обучения]] ✅ — review training script
- [[PyTorch/train_utils.py|train_utils.py]] ✅ — helper-функции обучения
- [[PyTorch/predict.py|predict.py]] ✅ — inference script
- [[PyTorch/Inference Pipeline|Inference Pipeline]] ✅ — полный prediction pipeline
- [[PyTorch/load_model()|load_model()]] ✅ — загрузка модели
- [[PyTorch/preprocess_image()|preprocess_image()]] ✅ — подготовка изображения
- [[PyTorch/predict()|predict()]] ✅ — функция предсказания
- [[PyTorch/top_k|top_k]] ✅ — несколько лучших классов
- [[PyTorch/Unsqueeze|Unsqueeze]] ✅ — `unsqueeze(0)` для batch dimension
- [[PyTorch/loss.item()|loss.item()]] ✅ — Tensor loss в Python number
- [[PyTorch/Weighted Average Loss|Weighted Average Loss]] ✅ — средний loss с учетом batch size
- [[PyTorch/Tuple Unpacking|Tuple Unpacking]] ✅ — распаковка нескольких return values

**Прогресс модуля GitHub File Analysis & Inference Pipeline:** 14/14 ключевых тем learned.
**Требует повторения:** размерности Tensor и параметр `dim`, внутренние преобразования `torchvision.transforms`, эффективность загрузки модели при многократных предсказаниях.

**PyTorch Foundations — Engineering Mindset & GitHub Project Analysis синхронизирован:**
- [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]] ✅ — чтение репозитория через архитектуру
- [[PyTorch/Как анализировать неизвестный код|Как анализировать неизвестный код]] ✅ — вопросы к незнакомому файлу
- [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]] ✅ — понимание проекта по структуре файлов
- [[PyTorch/Модель как универсальная функция|Модель как универсальная функция]] ✅ — модель как `features -> prediction`
- [[PyTorch/train.py как центр обучения|train.py как центр обучения]] ✅ — независимость train loop от источника данных
- [[PyTorch/PyTorch Dataset|Dataset]] ✅ и [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]] ✅ — replaceable Dataset через стабильный интерфейс
- [[PyTorch/Интерфейс важнее реализации|Интерфейс важнее реализации]] ✅ — interface over implementation
- [[PyTorch/Повторение терминов PyTorch Foundations|Повторение терминов PyTorch Foundations]] ✅ — связанный словарь модуля

**Прогресс модуля Engineering Mindset & GitHub Project Analysis:** 8/8 ключевых тем learned.
**Требует повторения:** самостоятельный анализ новых репозиториев, закрепление dependency flow между файлами, переход от tutorial-кода к production-коду.

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
