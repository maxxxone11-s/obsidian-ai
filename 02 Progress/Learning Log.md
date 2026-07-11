---
type: dashboard
tags:
  - dashboard
  - system
created: 2026-06-26
updated: 2026-07-11
---

# 📊 Журнал прогресса обучения

## 2026-07-11 (KNOWLEDGE_EXPORT sync: RAG — Production Architecture)

### ✅ Синхронизировано

- Экспорт `Retrieval Augmented Generation` синхронизирован в ранее подтверждённую Knowledge Area [[RAG/Index|RAG]]; новая область не создавалась.
- Обновлены существующие concept notes: [[RAG/Indexing Pipeline|Indexing Pipeline]], [[RAG/Query Pipeline|Query Pipeline]] и [[RAG/Document Loader|Document Loader]].
- Созданы полноценные concept notes: [[RAG/Orchestrator|Orchestrator]] и [[RAG/Query Transformation|Query Transformation]].
- Зафиксировано требование полной переиндексации при смене embedding-модели.
- Общие aliases `Workflow`, `Chain`, `Graph` и конфликтующий `Inference Pipeline` не добавлены; их смысл сохранён без создания неоднозначной навигации.
- Упомянутые техники Query Rewrite, Query Expansion, HyDE, Multi Query и Step-back Prompting оставлены unresolved wikilinks; пустые stubs не создавались.
- Обновлены Dashboard, Knowledge Map, Roadmap, RAG Plan и оба RAG Index.

### 🧠 Weak spots

- Требуется изучить конкретные техники Query Transformation.
- Требуется практическое понимание Prompt Builder.
- Требуется реализация полного Production RAG Pipeline на Python.

### Повторяющиеся ошибки

- Иногда смешиваются понятия текста, символов и результата работы Loader.
- Иногда объектом оценки называется документ вместо информации или контекста.

### Следующий шаг

- Изучить Query Rewrite, Query Expansion, HyDE, Multi Query и Step-back Prompting, затем реализовать полный Production RAG Pipeline в коде.

## 2026-07-11 (concept-name remediation)

### ✅ Обновлено

- Устранена неоднозначность Dataset: [[Neural Networks/Dataset для обучения модели|Dataset для обучения модели]] отделён от [[PyTorch/PyTorch Dataset|PyTorch Dataset]].
- Разделены статистическая [[Statistics/Z-score Standardization|Z-score Standardization]] и её ML-применение [[Machine Learning/Feature Standardization|Feature Standardization]].
- Разделены [[Neural Networks/Validation Set|Validation Set]] и [[LLM Engineering/Response Validation|Response Validation]].
- Материал из прежнего `Neural Networks/Overfitting.md` объединён с canonical [[Machine Learning/Overfitting|Overfitting]]; сохранены neural-network пример, простое объяснение и связи с Dropout, Validation Set и Test Set.
- Все pathless links `Dataset`, `Overfitting`, `Standardization` и `Validation` заменены path-qualified wikilinks по контексту.
- Обновлены area indexes, global Indexes, Dashboard, Knowledge Map и Roadmap.

### Результат

- Количество concept notes уменьшилось с 341 до 340 только за счёт объединения Overfitting.
- Domain-specific концепции больше не конкурируют за одинаковые pathless wikilinks.

### Следующий шаг

- Использовать только path-qualified wikilinks для концепций, чьи термины встречаются в нескольких Knowledge Areas.

## 2026-07-11 (аудит учебного диалога: RAG)

### ✅ Синхронизировано

- Полный учебный диалог RAG сопоставлен с текущим Vault; повторно уже синхронизированные концепции не создавались.
- Восстановлены пропущенные learned-концепции: [[RAG/Semantic Chunking]] и [[RAG/Reciprocal Rank Fusion (RRF)|Reciprocal Rank Fusion (RRF)]].
- [[RAG/Retrieval|Retrieval]] дополнен как подсистема, включающая semantic search, keyword search, fusion и Top-K в hybrid-сценарии.
- Начат блок Production RAG: созданы [[RAG/Document Loader|Document Loader]], [[RAG/Indexing Pipeline|Indexing Pipeline]], [[RAG/Query Pipeline|Query Pipeline]] и [[RAG/Production RAG Pipeline|Production RAG Pipeline]] со статусом `learning`, поскольку последний урок в диалоге не был завершён проверкой понимания.
- [[AI Engineering/Vector Database|Vector Database]] переведена из `draft` в `learning` и дополнена её ролью между indexing и query pipelines.
- Обновлены Dashboard, Knowledge Map, Roadmap, RAG Plan и оба RAG Index.
- Новые пустые stubs для упомянутых терминов не создавались.

### 🧠 Weak spots

- Не завершена проверка понимания различий между Indexing Pipeline и Query Pipeline.
- Требуется закрепить, что embedding объединённого текста не равен простому усреднению embeddings его частей.

### Повторяющиеся ошибки

- RRF сначала воспринимался как усреднение результатов, хотя он суммирует вклады, зависящие от rank.
- Ранее смешивались этапы предварительной индексации документов и обработки пользовательского запроса.

### Следующий шаг

- Завершить урок о Production RAG Pipeline, ответить на вопросы по Loader, индексации и участию LLM, затем перейти к практической реализации на Python.

## 2026-07-11 (KNOWLEDGE_EXPORT sync: RAG — Generation Evaluation)

### ✅ Синхронизировано

- Экспорт `Retrieval Augmented Generation` синхронизирован в canonical Knowledge Area [[RAG/Index|RAG]]; новая область не создавалась.
- Созданы concept-заметки: [[RAG/Faithfulness|Faithfulness]], [[RAG/Answer Relevancy|Answer Relevancy]], [[RAG/Context Precision|Context Precision]], [[RAG/Context Recall|Context Recall]], [[RAG/LLM-as-a-Judge|LLM-as-a-Judge]].
- Groundedness объединён с [[RAG/Faithfulness|Faithfulness]] как алиас; отдельная дублирующая заметка не создавалась.
- [[RAG/Plan|RAG Plan]] обновлён: этап Evaluation переведён в `learned`.
- Обновлены RAG Index, внешний RAG Index, Dashboard, Knowledge Map и Roadmap.
- Related-термины без учебного материала сохранены как unresolved wikilinks; пустые stubs не создавались.

### 🧠 Weak spots

- Требуется практическое понимание реализации LLM-as-a-Judge.
- Требуется изучение evaluation-фреймворков Ragas, DeepEval и LangSmith.
- Требуется изучение полного Production RAG Pipeline.

### Повторяющиеся ошибки

- Иногда используется термин «ответ» вместо «контекст» при объяснении Retrieval и Context Metrics.
- Иногда смешиваются уровни оценки Retrieval, Context и Generation.

### Следующий шаг

- Перейти к Production RAG Pipeline: Documents → Chunking → Embeddings → Vector Database → Retriever → Reranker → Prompt Construction → LLM → Answer, затем разобрать реализацию на Python и современных RAG-фреймворках.

## 2026-07-11 (KNOWLEDGE_EXPORT sync: RAG — Evaluation)

### ✅ Синхронизировано

- Экспорт `Retrieval Augmented Generation` синхронизирован в canonical Knowledge Area [[RAG/Index|RAG]]; новая область не создавалась.
- Созданы concept-заметки: [[RAG/Evaluation|Evaluation]], [[RAG/Ground Truth|Ground Truth]], [[RAG/Mean Reciprocal Rank (MRR)|Mean Reciprocal Rank (MRR)]], [[RAG/Hit Rate|Hit Rate]], [[RAG/Normalized Discounted Cumulative Gain (NDCG)|NDCG]].
- Обновлена существующая [[Machine Learning/Accuracy Precision Recall и F1|Accuracy, Precision, Recall и F1]]: добавлены retrieval-интерпретации Precision и Recall без создания дубликатов.
- [[RAG/Plan|RAG Plan]] обновлён: этап Evaluation переведён в `learning`.
- Обновлены RAG Index, внешний RAG Index, Dashboard, Knowledge Map и Roadmap.
- Related-термины без собственного материала сохранены как unresolved wikilinks; пустые stub-файлы не создавались.

### 🧠 Weak spots

- Требуется более глубокое понимание математической формулы NDCG.
- Требуется изучить Generation Evaluation без Ground Truth.
- Требуется изучить применение Retrieval Metrics к оценке reranker.

### Повторяющиеся ошибки

- Иногда используется слово «ответ» вместо «релевантный документ».
- Иногда путаются Rank и Reciprocal Rank.

### Следующий шаг

- Перейти к Generation Evaluation: Faithfulness, Answer Relevancy, Context Precision, Context Recall, LLM-as-a-Judge и Human Evaluation.

## 2026-07-11 (KNOWLEDGE_EXPORT sync: RAG — Retrieval Pipeline II)

### ✅ Синхронизировано

- Экспорт `Retrieval Augmented Generation` синхронизирован в ранее подтверждённую canonical Knowledge Area [[RAG/Index|RAG]]; новая область не создавалась.
- Созданы concept-заметки: [[RAG/Retrieval|Retrieval]], [[RAG/Top-K Retrieval|Top-K Retrieval]], [[RAG/Reranking|Reranking]], [[RAG/Hybrid Search|Hybrid Search]].
- [[RAG/Plan|RAG Plan]] обновлён: этапы Retrieval, Hybrid Search и Reranking переведены в `learning`.
- Обновлены RAG Index, внешний RAG Index, Dashboard, Knowledge Map и Roadmap.
- Отсутствующие related-термины сохранены как unresolved wikilinks; пустые stub-файлы не создавались.

### 🧠 Weak spots

- Пока отсутствует понимание конкретного алгоритма объединения результатов Hybrid Search через RRF.
- Требуется изучение метрик оценки качества Retrieval.

### Повторяющиеся ошибки

- Периодически используется термин «Top-K embeddings», хотя в LLM передаются найденные chunks, а embeddings используются только для поиска.

### Следующий шаг

- Изучить Reciprocal Rank Fusion (RRF), затем перейти к метрикам Evaluation: Recall, Precision, Hit Rate, MRR и NDCG.

## 2026-07-11 (KNOWLEDGE_EXPORT sync: RAG — Retrieval Pipeline)

### ✅ Синхронизировано

- Экспорт `Retrieval Augmented Generation` синхронизирован в подтверждённую canonical Knowledge Area [[RAG/Index|RAG]]; новая область не создавалась.
- Обновлены существующие concept-заметки: [[AI Engineering/RAG|Retrieval-Augmented Generation (RAG)]], [[AI Engineering/Embeddings|Embedding]], [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]].
- Созданы concept-заметки: [[RAG/Chunk|Chunk]], [[RAG/Fixed-size Chunking|Fixed-size Chunking]], [[RAG/Chunk Overlap|Chunk Overlap]], [[RAG/Recursive Chunking|Recursive Chunking]].
- [[RAG/Plan|RAG Plan]] переведён в `learning`; первые три этапа отмечены как частично изученные.
- Обновлены RAG Index, внешний RAG Index, Dashboard, Knowledge Map и Roadmap.
- Отсутствующие related-термины сохранены как unresolved wikilinks; пустые stub-файлы не создавались.

### 🧠 Weak spots

- Различие между внутренним Embedding Layer LLM и отдельной Embedding Model.
- Причины, по которым слишком большой overlap ухудшает систему.
- Почему мелкие единицы являются последним уровнем разделения в Recursive Chunking.

### Повторяющиеся ошибки

- Иногда смешивается работа Transformer внутри LLM и отдельных компонентов RAG.
- Иногда инженерные определения заменяются слишком общими формулировками вместо точного описания смысловой единицы.

### Следующий шаг

- Изучить Semantic Chunking и сравнить его с Recursive Chunking на реальных документах.

## 2026-07-10 (module plan: RAG)

### ✅ Обновлено

- Стабильная Knowledge Area [[RAG/Index|RAG]] инициализирована для обучения.
- Создан [[RAG/Plan|RAG Plan]] с 11 учебными блоками и финальным production-подобным проектом.
- Создан внешний [[Indexes/RAG Index|RAG Index]], обновлены Dashboard, Knowledge Map и Roadmap.
- `tag:#rag` уже присутствовал в Graph Groups; дублирующая группа не добавлялась.
- Concept-заметки и stub-файлы не создавались.
- Статистика concept notes не изменилась: всего 317, learned 258, needs_review 7, draft 52.

### Learning Path

- Почему появился RAG
- Embeddings
- Chunking
- Vector Database
- Retrieval
- Hybrid Search
- Reranking
- Generation
- Evaluation
- Production RAG
- Advanced RAG
- Финальный проект

### Следующий шаг

- Начать с проблемы, которую решает RAG: ограничений знаний LLM, hallucinations, Fine-tuning vs RAG и общей архитектуры системы.

## 2026-07-10 (KNOWLEDGE_EXPORT sync: LLM Engineering — Cost Optimization & Production Architecture)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[LLM Engineering/Index|LLM Engineering]].
- Созданы concept-заметки: [[LLM Engineering/Стоимость LLM-запросов|Стоимость LLM-запросов]], [[LLM Engineering/Cost Optimization|Cost Optimization]], [[LLM Engineering/Исключение ненужных вызовов LLM|Исключение ненужных вызовов LLM]], [[LLM Engineering/Model Routing|Model Routing]], [[LLM Engineering/Prompt Caching|Prompt Caching]], [[LLM Engineering/Production Pipeline LLM-приложения|Production Pipeline LLM-приложения]].
- [[LLM Engineering/Plan|LLM Engineering Plan]] обновлён: блок Cost Optimization переведён в `learned`, Production Pipeline добавлен в production architecture.
- LLM Engineering отмечен в Roadmap как `Foundation Completed`; следующим модулем выбран [[RAG/Index|RAG]].
- Отсутствующие related-термины сохранены как unresolved wikilinks; автоматические stub-заметки не создавались.
- Обновлены Dashboard, Knowledge Map, Roadmap и оба индекса LLM Engineering.

### 🧠 Weak spots

- Практическая реализация Semantic Cache.
- Реализация Model Router для сложных production-сценариев.
- Практические инструменты мониторинга стоимости запросов.

### Повторяющиеся ошибки

- Не выявлены.

### Следующий шаг

- Завершить LLM Engineering как Foundation Completed и перейти к модулю [[RAG/Index|RAG]], где будут использоваться знания о Context Window, Memory Management, Tool Calling и Production Pipeline.

## 2026-07-10 (KNOWLEDGE_EXPORT sync: LLM Engineering — Context Window & Memory Management)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[LLM Engineering/Index|LLM Engineering]].
- Созданы concept-заметки: [[LLM Engineering/Context Window|Context Window]], [[LLM Engineering/Переполнение Context Window|Переполнение Context Window]], [[LLM Engineering/Token Counting|Token Counting]], [[LLM Engineering/Conversation Memory|Conversation Memory]], [[LLM Engineering/Conversation State|Conversation State]], [[LLM Engineering/Memory Management|Memory Management]].
- [[LLM Engineering/Plan|LLM Engineering Plan]] обновлён: блок Context Engineering переведён в `learned` по изученным ключевым темам.
- Отсутствующие related-термины сохранены как unresolved wikilinks; автоматические stub-заметки не создавались.
- Обновлены Dashboard, Knowledge Map, Roadmap и оба индекса LLM Engineering.

### 🧠 Weak spots

- Практический расчёт токенов для сложных запросов.
- Реализация Summary и Sliding Window в production-коде.

### Повторяющиеся ошибки

- Не выявлены.

### Следующий шаг

- Перейти к блоку Cost Optimization, начиная с факторов, влияющих на стоимость запросов, и инженерных стратегий уменьшения расходов на использование LLM.

## 2026-07-10 (KNOWLEDGE_EXPORT sync: LLM Engineering — Function Calling & Streaming)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[LLM Engineering/Index|LLM Engineering]].
- Созданы concept-заметки: [[LLM Engineering/Function Calling|Function Calling]], [[LLM Engineering/Function Schema|Function Schema]], [[LLM Engineering/Tool Selection|Tool Selection]], [[LLM Engineering/Tool Loop|Tool Loop]], [[LLM Engineering/Multiple Tool Calls|Multiple Tool Calls]], [[LLM Engineering/Tool Calling|Tool Calling]], [[LLM Engineering/Streaming|Streaming]], [[LLM Engineering/Streaming API в OpenAI SDK|Streaming API в OpenAI SDK]], [[LLM Engineering/Streaming при Function Calling|Streaming при Function Calling]].
- [[LLM Engineering/Plan|LLM Engineering Plan]] обновлён: блоки Function Calling и Streaming переведены в `learned` по изученным ключевым темам.
- Обновлены Dashboard, Knowledge Map, Roadmap и оба индекса LLM Engineering.

### 🧠 Weak spots

- Не выявлены.

### Повторяющиеся ошибки

- Не выявлены.

### Следующий шаг

- Перейти к блоку Context Window, начиная с устройства окна контекста, ограничения количества токенов и управления историей диалога.

## 2026-07-10 (KNOWLEDGE_EXPORT sync: LLM Engineering Prompt Engineering & Structured Output)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[LLM Engineering/Index|LLM Engineering]].
- Созданы concept-заметки: [[LLM Engineering/Max Tokens|Max Tokens]], [[LLM Engineering/Stop Sequence|Stop Sequence]], [[LLM Engineering/Prompt Engineering|Prompt Engineering]], [[LLM Engineering/System Prompt|System Prompt]], [[LLM Engineering/User Prompt|User Prompt]], [[LLM Engineering/Prompt Templates|Prompt Templates]], [[LLM Engineering/Few-shot Prompting|Few-shot Prompting]], [[LLM Engineering/Delimiters|Delimiters]], [[LLM Engineering/Output Formatting|Output Formatting]], [[LLM Engineering/Structured Output|Structured Output]], [[LLM Engineering/JSON Schema|JSON Schema]], [[LLM Engineering/Pydantic в Structured Output|Pydantic в Structured Output]], [[LLM Engineering/Response Validation|Validation]], [[LLM Engineering/Error Recovery|Error Recovery]].
- [[LLM Engineering/Plan|LLM Engineering Plan]] обновлён: `max_tokens` и `stop` отмечены как learned; блоки Prompt Engineering и Structured Output переведены в learned по изученным темам.

### 🧠 Weak spots

- Отсутствуют.

### Повторяющиеся ошибки

- Отсутствуют.

### Следующий шаг

- Перейти к блоку Function Calling, начиная с архитектуры вызова функций и роли модели в принятии решения о необходимости вызова инструмента.

## 2026-07-08 (KNOWLEDGE_EXPORT sync: LLM Engineering API Integration)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[LLM Engineering/Index|LLM Engineering]].
- Созданы concept-заметки: [[LLM Engineering/OpenRouter через OpenAI SDK|OpenRouter через OpenAI SDK]], [[LLM Engineering/Архитектура OpenAI SDK|Архитектура OpenAI SDK]], [[LLM Engineering/Цепочка выполнения chat.completions.create|Цепочка выполнения chat.completions.create]], [[LLM Engineering/Messages как источник контекста модели|Messages как источник контекста модели]], [[LLM Engineering/Top-p (Nucleus Sampling)|Top-p (Nucleus Sampling)]].
- Обновлена существующая концепция: [[Transformers/Temperature Sampling|Temperature Sampling]].
- [[LLM Engineering/Plan|LLM Engineering Plan]] обновлён: блок "Основы LLM API" переведён в `learning`, изученные темы отмечены.

### 🧠 Weak spots

- Отсутствуют.

### Повторяющиеся ошибки

- Не выявлены.

### Следующий шаг

- Изучить параметры `max_tokens` и `stop`, затем перейти к Prompt Engineering.

## 2026-07-07 (module plan: LLM Engineering)

### ✅ Обновлено

- Создан module plan: [[LLM Engineering/Plan|LLM Engineering Plan]].
- Обновлены LLM Engineering indexes: [[LLM Engineering/Index|LLM Engineering Index]] и [[Indexes/LLM Engineering Index|Indexes/LLM Engineering Index]].
- Concept-заметки не создавались, статистика concept notes не увеличивалась.

### Learning Path

- Основы LLM API
- Prompt Engineering
- Structured Output
- Function Calling
- Streaming
- Context Engineering
- Cost Optimization
- Production Patterns
- Работа с несколькими провайдерами
- Финальный production-подобный сервис

### Следующий шаг

- Начать блок "Основы LLM API" и затем импортировать первые KNOWLEDGE_EXPORT targets как отдельные concept notes.

## 2026-07-07 (KNOWLEDGE_EXPORT sync: Transformers nanoGPT Source Code II)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]].
- Созданы concept-заметки: [[Transformers/CausalSelfAttention.forward Pipeline|CausalSelfAttention.forward Pipeline]], [[Transformers/Attention Tensor Shapes|Attention Tensor Shapes]].
- Обновлены существующие концепции: [[Transformers/Self-Attention Pipeline|Self-Attention Pipeline]], [[Transformers/Attention Scores|Attention Scores]], [[Transformers/Multi-Head Attention|Multi-Head Attention]], [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]], [[Transformers/Batch Matrix Multiplication|Batch Matrix Multiplication]], [[Transformers/Feed Forward Network|Feed Forward Network]], [[Transformers/Transformer Block|Transformer Block]].
- В [[Transformers/Formula Cards|Formula Cards]] добавлена только карточка FeedForward Expansion; существующие формулы не дублировались.

### 🧠 Weak spots

- Пока нет интуитивного понимания математического смысла операций внутри `QK^T` и последующих матричных преобразований.
- Сложно самостоятельно восстанавливать весь pipeline без просмотра кода.
- Требуется практика чтения исходного кода Transformer.

### Повторяющиеся ошибки

- Периодически смешиваются разные уровни кода: `GPT.forward`, `Block.forward` и `CausalSelfAttention.forward`.
- При чтении кода внимание иногда переключается на отдельные строки без удержания общего контекста текущего метода.

### Следующий шаг

- Завершить модуль Transformer на текущем уровне понимания и перейти к следующим модулям: LLM Engineering, RAG, AI Agents. Возвращаться к Transformer после накопления практического опыта и чтения production-кода.

## 2026-07-06 (KNOWLEDGE_EXPORT sync: Transformers nanoGPT Source Code)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]].
- Созданы concept-заметки: [[Transformers/GPTConfig|GPTConfig]], [[Transformers/ModuleList|ModuleList]].
- Обновлены существующие концепции: [[Transformers/Embedding Layer|Embedding Layer]], [[Transformers/Position Embedding|Position Embedding]], [[Transformers/nanoGPT Architecture|nanoGPT Architecture]], [[Transformers/Transformer Block|Transformer Block]], [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]].
- Не созданы отдельные заметки для `nn.Embedding` lookup, отличия `nn.Embedding` от обычного Tensor, WPE, `tok_emb + pos_emb`, Dropout после embedding и независимых весов blocks; материал слит в существующие concepts.

### 🧠 Weak spots

- Отличие `nn.Embedding` от обычного Tensor ещё не стало полностью интуитивным.
- Пока отсутствует уверенность в чтении кода PyTorch без объяснений.
- Не полностью сформировано понимание жизненного цикла `nn.Module` внутри модели.

### Повторяющиеся ошибки

- Склонность искать сложные вычисления там, где выполняется обычный lookup по таблице.
- Иногда воспринимать операции PyTorch как "магические", вместо анализа их инженерного назначения.

### Следующий шаг

- Продолжить разбор `GPT.forward()` строка за строкой, начиная с прохода через ModuleList и последующего выполнения каждого Transformer Block.

## 2026-07-04 (KNOWLEDGE_EXPORT sync: Transformers)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]]; новая Knowledge Area `Deep Learning` не создавалась.
- Созданы concept-заметки: [[Transformers/Causal Mask|Causal Mask]], [[Transformers/Веса как долговременная память модели|Веса как долговременная память модели]], [[Transformers/Разделение ролей LLM и RAG|Разделение ролей LLM и RAG]], [[Transformers/Weight Tying|Weight Tying]], [[Transformers/Autoregressive Generation|Autoregressive Generation]].
- Обновлены существующие концепции: [[Transformers/Attention Scores|Attention Scores]], [[Transformers/Query Key Value|Query Key Value]], [[Transformers/Language Modeling Head|Language Modeling Head]], [[Transformers/Embedding Layer|Embedding Layer]], [[Transformers/KV Cache|KV Cache]], [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]], [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]], [[Transformers/Self-Attention Pipeline|Self-Attention Pipeline]].
- Не созданы отдельные заметки для scaling через `sqrt(head_dim)`, семантики QKV и Transformer как последовательности преобразований представлений; материал слит в существующие concepts.

### 🧠 Weak spots

- Интуитивная связь математических операций: матричное умножение, Softmax, Linear и общая архитектурная логика.
- Геометрическая интерпретация пространства embedding и переходов между пространствами.
- Глубокое понимание того, почему Linear лучше прямого поиска ближайшего embedding.

### Повторяющиеся ошибки

- Иногда интерпретировать embedding как постоянное хранилище знаний модели.
- Иногда смешивать параметры модели и embedding документов в RAG.

### Следующий шаг

- Перейти к механизму обучения Transformer: Teacher Forcing, Cross Entropy Loss, Backpropagation и обновлению весов, чтобы замкнуть полный цикл `данные -> Transformer -> logits -> ошибка -> изменение весов`.

## 2026-07-03 (KNOWLEDGE_EXPORT sync: Transformer architecture module)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]]; новая Knowledge Area `Deep Learning` не создавалась.
- Созданы concept-заметки: [[Transformers/Position Embedding|Position Embedding]], [[Transformers/Pre-LayerNorm|Pre-LayerNorm]], [[Transformers/Transformer Block Interface|Transformer Block Interface]], [[Transformers/nn.Module __call__|nn.Module __call__]], [[Transformers/Self-Attention Pipeline|Self-Attention Pipeline]].
- Обновлены существующие концепции: [[Transformers/Embedding Layer|Embedding Layer]], [[Transformers/Residual Connection|Residual Connection]], [[Transformers/LayerNorm|LayerNorm]], [[Transformers/Query Key Value|Query Key Value]], [[Transformers/Multi-Head Attention|Multi-Head Attention]].
- Implementation details не вынесены в отдельные заметки: сложение вместо concat, Residual Philosophy, `c_attn`, output projection и роль `c_proj` слиты в существующие concepts.

### 🧠 Weak spots

- Перестановка размерностей `transpose` при переходе к Multi-Head Attention.
- Интуитивное понимание матричного умножения по последним двум осям.
- Размерности тензоров на каждом этапе вычислений.

### Следующий шаг

- Разобрать оставшуюся реализацию `CausalSelfAttention.forward()` до конца, включая масштабирование, causal mask и финальный Output Projection в исходном коде nanoGPT.

## 2026-07-03 (KNOWLEDGE_EXPORT sync: Transformers generation module)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]]; новая Knowledge Area `Deep Learning` не создавалась.
- Созданы concept-заметки: [[Transformers/KV Cache|KV Cache]], [[Transformers/Attention Complexity During Inference|Attention Complexity During Inference]], [[Transformers/Language Modeling Head|Language Modeling Head]], [[Transformers/Temperature Sampling|Temperature Sampling]], [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]], [[Transformers/nanoGPT Architecture|nanoGPT Architecture]].
- Обновлена существующая концепция: [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]].
- Связи добавлены с [[Neural Networks/Logits|Logits]], [[Neural Networks/Softmax|Softmax]], [[RAG/Index|RAG]], [[Transformers/Query Key Value|Query Key Value]] и [[Transformers/Transformer Block|Transformer Block]].

### 🧠 Weak spots

- Путаница между памятью приложения и KV Cache.
- Представление о создании независимых экземпляров классов в цикле Python.
- Практическое чтение исходного кода nanoGPT.

### Следующий шаг

- Полностью разобрать метод `GPT.forward()` из nanoGPT строка за строкой и сопоставить каждую инструкцию с изученными архитектурными компонентами.

## 2026-07-02 (KNOWLEDGE_EXPORT sync: Transformer Foundations IV)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]].
- Concept Test выполнен: создана только самостоятельная concept-заметка [[Transformers/Multi-Head Attention|Multi-Head Attention]].
- Head Projection, Output Projection, Tensor Reshaping и объединение `batch × heads` не вынесены в отдельные concept-заметки; материал слит в [[Transformers/Multi-Head Attention|Multi-Head Attention]], [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]], [[Transformers/Batch Matrix Multiplication|Batch Matrix Multiplication]] и [[Transformers/Query Key Value|Query Key Value]].

### 🧠 Weak spots

- Полная реализация `multi_head_attention_forward()`.
- Работа Attention Mask.
- Работа Padding Mask.
- Decoder Self-Attention.

### Следующий шаг

- Разобрать исходный код `multi_head_attention_forward()` полностью.
- Изучить Attention Mask, Causal Mask и Padding Mask.
- Перейти к архитектурным различиям Encoder и Decoder.

## 2026-07-01 (KNOWLEDGE_EXPORT sync: Transformer Foundations III)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]].
- Обновлены существующие concept-заметки по Knowledge Synchronization Protocol 2.1: [[Transformers/LayerNorm|LayerNorm]], [[Transformers/Residual Connection|Residual Connection]], [[Transformers/Feed Forward Network|Feed Forward Network]].
- Тема "Причина расположения LayerNorm после Residual Connection" не вынесена в отдельную concept-заметку; знание слито в [[Transformers/LayerNorm|LayerNorm]] и [[Transformers/Residual Connection|Residual Connection]].
- [[Transformers/LayerNorm|LayerNorm]] переведен из `needs_review` в `learned`, так как learning_state указывает понимание математической связи LayerNorm и z-score, назначения `γ` и `β`, а также инженерной причины применения LayerNorm после Residual.

### 🧠 Weak spots

- Различия между Post-LN и Pre-LN архитектурами.
- Внутренняя реализация LayerNorm в PyTorch.
- Практическое влияние `γ` и `β` во время обучения.

### Следующий шаг

- Изучить Multi-Head Attention.
- Разобрать реализацию MultiHeadAttention в исходном коде PyTorch.
- Изучить различия между Single Head и Multi-Head Attention.
- Начать анализ полного Transformer Block в современных LLM.

## 2026-07-01 (KNOWLEDGE_EXPORT sync: Statistics Foundations for Machine Learning — Formula Update)

### ✅ Синхронизировано

- Формулы добавлены в существующие concept-заметки области [[Statistics/Index|Statistics]] без создания дублей.
- Обновлены заметки: [[Statistics/Mean|Mean]], [[Statistics/Variance|Variance]], [[Statistics/Standard Deviation|Standard Deviation]], [[Statistics/Min-Max Normalization|Min-Max Normalization]], [[Statistics/Z-score Standardization|Standardization]], [[Statistics/Z-score|Z-score]], [[Statistics/Normal Distribution|Normal Distribution]].
- `Math Statistic` не создавался как новая Knowledge Area; обновление применено к подтвержденной области [[Statistics/Index|Statistics]].

### Следующий шаг

- Использовать формулы Statistics при разборе [[Transformers/LayerNorm|LayerNorm]], Z-score outlier detection и preprocessing в NumPy, pandas и scikit-learn.

## 2026-07-01 (KNOWLEDGE_EXPORT sync: Statistics Foundations for Machine Learning)

### ✅ Синхронизировано

- Создана новая Knowledge Area [[Statistics/Index|Statistics]] по явному подтверждению пользователя.
- Модуль синхронизирован в `Statistics`, не в `Math Statistic`.
- Созданы concept-заметки: [[Statistics/Mean|Mean]], [[Statistics/Variance|Variance]], [[Statistics/Причина использования квадратов в статистике|Причина использования квадратов в статистике]], [[Statistics/Standard Deviation|Standard Deviation]], [[Statistics/Min-Max Normalization|Min-Max Normalization]], [[Statistics/Z-score Standardization|Standardization]], [[Statistics/Z-score|Z-score]], [[Statistics/Normal Distribution|Normal Distribution]], [[Statistics/Связь основных статистических понятий|Связь основных статистических понятий]].
- Созданы обзорные индексы: [[Statistics/Index|Statistics Index]] и [[Indexes/Statistics Index|Statistics Index]].
- Связи проставлены на существующие темы [[Machine Learning/Feature Scaling|Feature Scaling]], [[Machine Learning/Normalization|Normalization]], [[Machine Learning/Feature Standardization|Standardization]], [[Machine Learning/Mathematics/MSE|MSE]] и [[Transformers/LayerNorm|LayerNorm]].

### 🧠 Weak spots

- Различие между Standardization и Normalization в терминологии.
- Интерпретация Standard Deviation как возврата к исходным единицам измерения.

### Следующий шаг

- Изучить поиск выбросов с помощью Z-score.
- Разобрать статистическую подготовку данных в NumPy, pandas и scikit-learn.
- Закрепить знания на практических задачах с реальными датасетами.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: Transformer Foundations II)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Transformers/Index|Transformers]].
- Созданы concept-заметки: [[Transformers/Transformer Block|Transformer Block]], [[Transformers/Residual Connection|Residual Connection]], [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]], [[Transformers/Feed Forward Network|Feed Forward Network]], [[Transformers/Module и Functional в PyTorch|Module и Functional в PyTorch]], [[Transformers/Batch Matrix Multiplication|Batch Matrix Multiplication]], [[Transformers/LayerNorm|LayerNorm]].
- Обновлены существующие концепции: [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]] и [[Transformers/Embedding Space|Embedding Space]].
- Тема реализации QKV через объединенную матрицу весов не вынесена в отдельную concept-заметку; знание слито в [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]].

### 🧠 Weak spots

- Математическая природа LayerNorm.
- Статистический смысл нормализации.
- Полный цикл вычислений внутри LayerNorm.

### Следующий шаг

- Изучить модуль статистики: Mean, Variance, Standard Deviation, Normalization и Z-score.
- Вернуться к Transformer и полностью разобрать LayerNorm.
- Продолжить чтение исходного кода MultiHeadAttention из PyTorch.
- Перейти к Multi-Head Attention и полной реализации Transformer Block.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: Transformer Foundations I)

### ✅ Синхронизировано

- Создана новая Knowledge Area [[Transformers/Index|Transformers]] по явному подтверждению пользователя.
- Модуль синхронизирован в `Transformers`, не в `Neural Networks`.
- Созданы concept-заметки: [[Transformers/Embedding Layer|Embedding Layer]], [[Transformers/Статический и контекстный Embedding|Статический и контекстный Embedding]], [[Transformers/Query Key Value|Query Key Value]], [[Transformers/Attention Scores|Attention Scores]], [[Transformers/Attention Weights|Attention Weights]], [[Transformers/Attention Output|Attention Output]], [[Transformers/Embedding Space|Embedding Space]], [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]].
- Созданы обзорные индексы: [[Transformers/Index|Transformers Index]] и [[Indexes/Transformers Index|Transformers Index]].
- Связи проставлены на существующие темы [[Neural Networks/Softmax|Softmax]] и [[PyTorch/nn.Linear|nn.Linear]] без создания дублей.

### 🧠 Weak spots

- Геометрическая интерпретация embedding space.
- Интуитивное понимание изменения embedding после каждого слоя.
- Математическая связь Scores → Softmax → Weighted Sum.
- Связь нескольких Transformer Block с постепенным уточнением embedding.

### Следующий шаг

- Изучить полный Transformer Block: Residual Connection, LayerNorm, FeedForward.
- Разобрать реальную реализацию MultiHeadAttention из исходников PyTorch.
- Реализовать упрощенный SelfAttention вручную на PyTorch без использования `nn.MultiheadAttention`.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: PyTorch Foundations — Engineering Mindset & GitHub Project Analysis)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[PyTorch/Index|PyTorch]]; новая Knowledge Area `ML Engineering` не создавалась.
- Созданы concept-заметки: [[PyTorch/Как анализировать неизвестный код|Как анализировать неизвестный код]], [[PyTorch/Модель как универсальная функция|Модель как универсальная функция]], [[PyTorch/Интерфейс важнее реализации|Интерфейс важнее реализации]], [[PyTorch/Повторение терминов PyTorch Foundations|Повторение терминов PyTorch Foundations]].
- Обновлены существующие концепции: [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]], [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]], [[PyTorch/train.py как центр обучения|train.py как центр обучения]], [[PyTorch/PyTorch Dataset|Dataset]], [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]], [[PyTorch/Separation of Concerns|Separation of Concerns]], [[Neural Networks/Model|Model]].
- Темы про независимость `train.py` от Dataset, заменяемость Dataset и interface over implementation связаны с существующими PyTorch architecture/data pipeline заметками.

### 🧠 Weak spots

- Нужно закрепить навык самостоятельного анализа новых репозиториев без подсказок.
- Нужно чаще отслеживать dependency flow между файлами.
- Требуется практика перехода от tutorial-кода к production-коду.

### Следующий шаг

- Перейти к production ML и Transformer/Hugging Face репозиториям; при чтении начинать со структуры проекта, ответственности файлов и интерфейсов между компонентами.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: PyTorch Foundations — GitHub File Analysis & Inference Pipeline)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[PyTorch/Index|PyTorch]].
- Созданы concept-заметки: [[PyTorch/train_utils.py|train_utils.py]], [[PyTorch/predict.py|predict.py]], [[PyTorch/Inference Pipeline|Inference Pipeline]], [[PyTorch/load_model()|load_model()]], [[PyTorch/preprocess_image()|preprocess_image()]], [[PyTorch/predict()|predict()]], [[PyTorch/top_k|top_k]], [[PyTorch/loss.item()|loss.item()]], [[PyTorch/Weighted Average Loss|Weighted Average Loss]], [[PyTorch/Tuple Unpacking|Tuple Unpacking]].
- Обновлены существующие концепции: [[PyTorch/model.py как отдельная ответственность|model.py как отдельная ответственность]], [[PyTorch/train.py как центр обучения|train.py как центр обучения]], [[PyTorch/Unsqueeze|Unsqueeze]], [[Neural Networks/Softmax|Softmax]], [[Neural Networks/Inference|Inference]], [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]], [[Neural Networks/torch.no_grad()|torch.no_grad()]], [[PyTorch/model.eval()|model.eval()]], [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]].
- `softmax(dim=1)` не вынесен в отдельную concept-заметку; знание слито в [[Neural Networks/Softmax|Softmax]] и связано с [[PyTorch/Inference Pipeline|Inference Pipeline]].
- `unsqueeze(0)` не вынесен в отдельную concept-заметку; знание слито в [[PyTorch/Unsqueeze|Unsqueeze]] и [[PyTorch/preprocess_image()|preprocess_image()]].

### 🧠 Weak spots

- Требуется практика с различными размерностями Tensor и параметром `dim`.
- Нужно закрепить понимание внутренних преобразований `torchvision.transforms`.
- Следует глубже изучить эффективность загрузки модели при многократных предсказаниях.

### Следующий шаг

- Изучить production-проекты с Transformer и современными архитектурами; разобрать checkpoint, state_dict и полный inference pipeline; перейти к Hugging Face Transformers и PyTorch Lightning.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: PyTorch Foundations — Loss, Optimization & Autograd)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[PyTorch/Index|PyTorch]].
- Созданы concept-заметки: [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]], [[PyTorch/model.parameters()|model.parameters()]].
- Обновлены существующие концепции: [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]], [[Neural Networks/Logits|Logits]], [[Neural Networks/Adam|Adam]], [[PyTorch/torch.optim|torch.optim]], [[PyTorch/Autograd|Autograd]], [[Neural Networks/torch.no_grad()|torch.no_grad()]], [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]], [[PyTorch/model.eval()|model.eval()]], [[PyTorch/DataLoader|DataLoader]], [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]].
- `Softmax внутри CrossEntropyLoss` не вынесен в отдельную concept-заметку; знание слито в [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]].
- `DataLoader под капотом` не вынесен в отдельную concept-заметку; знание слито в [[PyTorch/DataLoader|DataLoader]].

### 🧠 Weak spots

- Требуется более глубокое понимание внутреннего устройства Adam.
- Требуется понимание математической основы CrossEntropyLoss.
- Пока не полностью сформирована интуиция хранения промежуточных значений в вычислительном графе.
- Требуется практика анализа DataLoader на уровне реализации.

### Следующий шаг

- Изучить train_utils.py и inference pipeline; разобрать predict.py и полный процесс использования обученной модели; перейти к анализу реальных GitHub-проектов с Transformer и современными архитектурами.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: PyTorch Foundations — GitHub Projects & ML Architecture)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[PyTorch/Index|PyTorch]].
- Созданы concept-заметки: [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]], [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]], [[PyTorch/model.py как отдельная ответственность|model.py как отдельная ответственность]], [[PyTorch/train.py как центр обучения|train.py как центр обучения]], [[PyTorch/config.py|config.py]], [[PyTorch/Separation of Concerns|Separation of Concerns]], [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]].
- Обновлены существующие концепции: [[PyTorch/Чтение архитектуры PyTorch-проектов|Чтение архитектуры PyTorch-проектов]], [[PyTorch/nn.Module|nn.Module]], [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]], [[PyTorch/PyTorch Dataset|Dataset]], [[PyTorch/DataLoader|DataLoader]], [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]].
- Тема "Гиперпараметры vs параметры датасета" не вынесена в отдельную concept-заметку; знание слито в [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]] и связано с [[PyTorch/config.py|config.py]].

### 🧠 Weak spots

- Пока нет практического опыта чтения крупных репозиториев.
- Требуется больше практики анализа архитектуры без подсказок.
- Пока не сформирована интуиция выбора значений `hidden_size`.

### Следующий шаг

- Изучить внутреннюю реализацию CrossEntropyLoss, Adam, `backward()` и DataLoader; продолжить разбор реальных GitHub-файлов: train_utils.py, predict.py и inference pipeline.

## 2026-06-30 (KNOWLEDGE_EXPORT sync: PyTorch Foundations III)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[PyTorch/Index|PyTorch]].
- Созданы concept-заметки: [[PyTorch/Многослойная нейронная сеть|Многослойная нейронная сеть]], [[PyTorch/Анализ архитектуры модели по слоям|Анализ архитектуры модели по слоям]], [[PyTorch/Чтение архитектуры PyTorch-проектов|Чтение архитектуры PyTorch-проектов]].
- Обновлены существующие концепции: [[Neural Networks/Train Validation Test|Train Validation Test]], [[PyTorch/nn.Module|nn.Module]], [[Neural Networks/ReLU|ReLU]], [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]], [[PyTorch/model.eval()|model.eval()]], [[Neural Networks/Output|Output]], [[PyTorch/nn.Linear|nn.Linear]].
- Правило "последний слой определяется задачей" не вынесено в отдельную concept-заметку; знание слито в [[Neural Networks/Output|Output]] и [[PyTorch/nn.Linear|nn.Linear]].

### 🧠 Weak spots

- Пока нет уверенности в выборе последнего слоя для разных типов классификации.
- Недостаточное понимание связи между последним слоем и функцией потерь.
- Требуется закрепление анализа архитектуры на реальных GitHub-проектах.

### Следующий шаг

- Изучить Loss Functions: MSELoss, CrossEntropyLoss, BCEWithLogitsLoss; разобрать [[torch.no_grad()]]; читать реальные PyTorch-проекты с GitHub параллельно с оставшимися темами фундамента.

## 2026-06-29 (KNOWLEDGE_EXPORT sync: Graph Theory Foundations I)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Algorithms/Index|Algorithms & Data Structures]].
- Обновлены существующие концепции: [[Algorithms/Graph Theory/Basics/Что такое граф|Что такое граф]], [[Algorithms/Graph Theory/Basics/Вершины и ребра|Вершины и ребра]], [[Algorithms/Graph Theory/Basics/Изолированная вершина|Изолированная вершина]], [[Algorithms/Graph Theory/Basics/Удаление вершины и удаление ребра|Удаление вершины и удаление ребра]], [[Algorithms/Graph Theory/Basics/Ориентированный и неориентированный граф|Ориентированный и неориентированный граф]], [[Algorithms/Graph Theory/Basics/Путь|Путь]], [[Algorithms/Graph Theory/Trees/Дерево|Дерево]], [[Algorithms/Graph Theory/Trees/Root Parent Child Leaf|Root Parent Child Leaf]], [[Algorithms/Graph Theory/Basics/Цикл|Цикл]], [[Algorithms/Graph Theory/DAG/DAG|DAG]].
- Создана новая concept-заметка: [[Algorithms/Graph Theory/Basics/Список смежности|Список смежности]].
- Обновлена обзорная заметка [[Algorithms/Graph Theory/Basics/Представление графов в памяти|Представление графов в памяти]] ссылкой на список смежности.

### 🧠 Weak spots

- Пока еще не полностью сформировано понимание строгого определения дерева.
- Пока не изучены альтернативные способы хранения графов.
- Пока отсутствует понимание сложности операций Big O для графов.

### Следующий шаг

- Изучить матрицу смежности, сравнить список смежности и матрицу смежности, научиться выбирать способ хранения графа в зависимости от задачи.

## 2026-06-29 (KNOWLEDGE_EXPORT sync: Рекурсия на деревьях)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[Algorithms/Index|Algorithms & Data Structures]].
- Созданы concept-заметки: [[Algorithms/Recursion/Trees/Дерево как рекурсивная структура данных|Дерево как рекурсивная структура данных]], [[Algorithms/Recursion/Trees/DFS на дереве|DFS на дереве]], [[Algorithms/Recursion/Trees/Рекурсия с возвратом результата из поддерева|Рекурсия с возвратом результата из поддерева]], [[Algorithms/Recursion/Trees/Подсчет количества узлов дерева|Подсчет количества узлов дерева]], [[Algorithms/Recursion/Trees/Поиск максимальной глубины дерева|Поиск максимальной глубины дерева]].
- Обновлены связи в [[Algorithms/Tree|Tree]], [[Algorithms/DFS|DFS]], [[Algorithms/Recursion/Trees/Tree Traversal|Tree Traversal]], [[Algorithms/Recursion/Trees/Binary Tree Traversal|Binary Tree Traversal]] и [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]].

### 🧠 Weak spots

- Объединение результатов нескольких рекурсивных вызовов.
- Понимание момента, когда использовать сумму, а когда максимум.
- Склонность совмещать несколько способов решения: цикл и генератор.
- Игнорирование возвращаемого значения рекурсивного вызова.
- Двойной подсчет текущего узла.

### Следующий шаг

- Отработать подсчет листьев, поиск значения в дереве, возврат пути до узла, preorder/postorder traversal и переход к бинарным деревьям.

## 2026-06-28 (KNOWLEDGE_EXPORT sync: PyTorch Foundations II)

### ✅ Синхронизировано

- Модуль синхронизирован в существующую область [[PyTorch/Index|PyTorch]].
- Созданы новые concept-заметки: [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch (matmul)]], [[PyTorch/nn.Linear|nn.Linear]], [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]].
- Обновлены существующие заметки: [[PyTorch/Autograd|Autograd]], [[Machine Learning/Gradient Descent|Gradient Descent]], [[Machine Learning/Loss Function|Loss Function]], [[Machine Learning/Mathematics/Производная|Производная]], [[PyTorch/Tensors/Tensor Operations|Tensor Operations]], [[PyTorch/nn.Module|nn.Module]].
- `Derivatives for AI` не создавался как новая Knowledge Area; материал слит в [[Machine Learning/Mathematics/Производная|Производная]].

### 🧠 Weak spots

- Производные сложных функций и [[Neural Networks/Chain Rule|Chain Rule]].
- Более глубокое понимание computation graph.
- Момент появления gradient: `backward()` вычисляет градиенты, `optimizer.step()` обновляет веса.
- Порядок вызовов в [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]].

### Следующий шаг

- Закрепить [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]] на маленькой модели: `nn.Linear → loss → zero_grad → backward → step`.

## 2026-06-27 (Full Knowledge Synchronization)

### ✅ Синхронизировано

- Просканированы все concept-заметки Vault.
- Удалены устаревшие `Импорт KNOWLEDGE_EXPORT` блоки из concept-заметок.
- Поля из старых import-блоков объединены с существующими canonical-разделами.
- Удалены дубли canonical-разделов и generated footers внутри учебных заметок.
- Индексы очищены от старой import-терминологии.

### Результат проверки

- Concept-заметок: 197.
- Дубли canonical-секций: 0.
- Import-блоки в concept-заметках: 0.
- Служебные generated footers внутри concept-заметок: 0.

### Следующий шаг

- В следующих KNOWLEDGE_EXPORT выполнять только синхронизацию существующих концепций: one concept, one note, one truth.

## 2026-06-27 (Рефакторинг Vault: одна концепция = одна заметка)

### ✅ Обновлено

- [[Machine Learning/Feature Scaling|Feature Scaling]] превращён в overview/index с пометкой, что материал разнесён по отдельным заметкам.
- Обновлены и выделены отдельные концепции: [[Machine Learning/Normalization|Normalization]], [[Machine Learning/Feature Standardization|Standardization]], [[Machine Learning/Fit Transform и Data Leakage|Fit Transform и Data Leakage]], [[Machine Learning/Scaling и Gradient Descent|Scaling и Gradient Descent]], [[Machine Learning/Scaling для KNN и SVM|Scaling для KNN и SVM]], [[Machine Learning/Scaling и Tree-Based Models|Scaling и Tree-Based Models]].
- [[Machine Learning/Loss Function|Loss Function]] превращён в overview по функциям потерь.
- Обновлены loss-концепции: [[Machine Learning/Mathematics/MSE|MSE]], [[Machine Learning/Mathematics/MAE|MAE]], [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]].
- [[AI Agents/Index|AI Agents Index]] очищен от полного импорта LangGraph и оставлен как короткий overview со ссылкой на [[LangGraph/Index]].

### Следующий шаг

- Читать ML preprocessing через [[Machine Learning/Feature Scaling|Feature Scaling]] как карту, а детали открывать в отдельных concept-заметках.

## 2026-06-27 (KNOWLEDGE_EXPORT: Python — Рекурсия)

### ✅ Импортировано

- Модуль импортирован в существующую область [[Algorithms/Index|Algorithms & Data Structures]] во внутреннюю структуру [[Algorithms/Recursion/Index|Algorithms/Recursion]].
- Созданы основные концепции: [[Algorithms/Recursion/Basics/Recursion|Recursion]], [[Algorithms/Recursion/Basics/Base Case|Base Case]], [[Algorithms/Recursion/Internals/Call Stack|Call Stack]], [[Algorithms/Recursion/Patterns/Recursive Return Chain|Recursive Return Chain]].
- Созданы примеры: [[Algorithms/Recursion/Examples/Factorial|Factorial]], [[Algorithms/Recursion/Examples/Рекурсивная сумма чисел|Рекурсивная сумма чисел]], [[Algorithms/Recursion/Examples/Рекурсивный разворот строки|Рекурсивный разворот строки]], [[Algorithms/Recursion/Examples/Рекурсивная проверка палиндрома|Рекурсивная проверка палиндрома]].
- Созданы stub-заметки: [[Algorithms/Recursion/Patterns/Recursive Thinking|Recursive Thinking]], [[Algorithms/Recursion/Patterns/Recursion Patterns|Recursion Patterns]], [[Algorithms/Recursion/Patterns/Divide and Conquer|Divide and Conquer]], [[Algorithms/Recursion/Examples/String Slicing in Recursion|String Slicing in Recursion]], [[Algorithms/Recursion/Trees/Tree Traversal|Tree Traversal]], [[Algorithms/Recursion/Trees/Binary Tree Traversal|Binary Tree Traversal]].
- Обновлены связи в [[Algorithms/DFS|DFS]], [[Algorithms/Stack|Stack]] и [[Algorithms/Tree|Tree]].

### 🧠 Weak spots

- Рекурсия на деревьях.
- Рекурсия на графах.
- Сложные рекурсивные задачи LeetCode.
- Неточности в использовании срезов строк.
- Иногда путается терминология «вызов» и «возврат».

### Следующий шаг

- Повторить [[Algorithms/Recursion/Examples/String Slicing in Recursion|String Slicing in Recursion]], затем перейти к [[Algorithms/Recursion/Trees/Tree Traversal|Tree Traversal]] и [[Algorithms/DFS|DFS]].

## 2026-06-27 (KNOWLEDGE_EXPORT: PyTorch — Tensor Fundamentals)

### ✅ Импортировано

- Модуль импортирован в существующую область [[PyTorch/Index|PyTorch]].
- Создана внутренняя структура [[PyTorch/Tensors/Index|PyTorch/Tensors]].
- Обновлены концепции: [[PyTorch/Tensor|Tensor]], [[PyTorch/Shape|Tensor Shape]], [[PyTorch/Reshape|Reshape]], [[PyTorch/View|View]], [[PyTorch/Unsqueeze|Unsqueeze]], [[PyTorch/Squeeze|Squeeze]], [[PyTorch/Broadcasting|Broadcasting]].
- Созданы концепции: [[PyTorch/Tensors/Tensor Dimensions (ndim)|Tensor Dimensions (ndim)]], [[PyTorch/Tensors/Tensor Creation|Tensor Creation]], [[PyTorch/Tensors/Tensor Dtype|Tensor Dtype]], [[PyTorch/Tensors/Tensor Indexing and Slicing|Tensor Indexing and Slicing]].
- Созданы stub-заметки: [[PyTorch/Tensors/Tensor Operations|Tensor Operations]], [[PyTorch/PyTorch Dataset|Dataset]], [[PyTorch/DataLoader|DataLoader]].

### 🧠 Weak spots

- [[PyTorch/Broadcasting|Broadcasting]].
- Shape после сложных операций slicing.
- Мысленное выравнивание размерностей справа налево.
- Не считать элементы вместо структуры.
- Не путать строки и столбцы.
- Читать `Tensor[rows, columns]`, где запятая разделяет оси.

### Следующий шаг

- Повторить [[PyTorch/Broadcasting|Broadcasting]] и [[PyTorch/Tensors/Tensor Indexing and Slicing|Tensor Indexing and Slicing]], затем перейти к [[PyTorch/Tensors/Tensor Operations|Tensor Operations]] и [[PyTorch/Autograd|Autograd]].

## 2026-06-27 (KNOWLEDGE_EXPORT: Основы теории графов)

### ✅ Импортировано

- Создана структура [[Algorithms/Graph Theory/Index|Graph Theory]]: Basics, Trees, DAG.
- Созданы концепции: [[Algorithms/Graph Theory/Basics/Что такое граф|Что такое граф]], [[Algorithms/Graph Theory/Basics/Вершины и ребра|Вершины и ребра]], [[Algorithms/Graph Theory/Basics/Изолированная вершина|Изолированная вершина]], [[Algorithms/Graph Theory/Basics/Удаление вершины и удаление ребра|Удаление вершины и удаление ребра]], [[Algorithms/Graph Theory/Basics/Ориентированный и неориентированный граф|Ориентированный и неориентированный граф]], [[Algorithms/Graph Theory/Basics/Путь|Путь]], [[Algorithms/Graph Theory/Trees/Дерево|Дерево]], [[Algorithms/Graph Theory/Trees/Root Parent Child Leaf|Root Parent Child Leaf]], [[Algorithms/Graph Theory/Basics/Цикл|Цикл]], [[Algorithms/Graph Theory/DAG/DAG|DAG]].
- Обновлены [[Algorithms/Graphs|Graphs]] и [[Algorithms/Tree|Tree]] связями на Graph Theory.

### 🧠 Weak spots

- Более строгое определение дерева.
- Связь дерева и DAG.
- Почему отсутствие нескольких путей является следствием отсутствия циклов.
- Склонность придумывать связи, которых нет в условии.

### Следующий шаг

- Перейти к представлению графов в памяти: adjacency list, adjacency matrix и обходы [[Algorithms/DFS|DFS]] / [[Algorithms/BFS|BFS]].

## 2026-06-26 (Аудит правил KNOWLEDGE_EXPORT)

### ✅ Обновлено

- В [[AGENTS]] добавлены обязательные правила обновления Dashboard, Knowledge Map, Roadmap, Learning Log и соответствующего `Indexes/*` после каждого KNOWLEDGE_EXPORT.
- [[00 Dashboard/Dashboard|Dashboard]] пересчитан по текущим `type: concept`: всего 147, learned 94, learning 0, needs_review 2, draft 51.
- [[00 Dashboard/Knowledge Map|Knowledge Map]] пересобран по текущим учебным разделам без дублей.
- [[01 Roadmap/Roadmap|Roadmap]] дополнен аудитом правил импорта.

### Следующий шаг

- При каждом следующем импорте сначала обновлять концепции, затем обязательно синхронизировать модульный статус и обзорные файлы.

## 2026-06-26 (Проверка импорта: Machine Learning Fundamentals)

### ✅ Проверено

- Найдены ключевые темы Machine Learning Fundamentals: 23.
- Статусы: 22 learned, 1 needs_review ([[Parameters и Hyperparameters]]).
- Модуль Machine Learning Fundamentals отмечен в [[01 Roadmap/Roadmap|Roadmap]] как пройденный.
- Обновлена статистика в [[00 Dashboard/Dashboard|Dashboard]].

### 🔁 Повторить

- [[Parameters и Hyperparameters]] — различие между обучаемыми parameters и задаваемыми hyperparameters.

## 2026-06-26 (KNOWLEDGE_EXPORT: Machine Learning Fundamentals)

### ✅ Импортировано

- Добавлен фундамент ML: [[Что такое Machine Learning]], [[Dataset, Features и Labels]], [[Data Leakage]].
- Обновлены supervised learning и optimization темы: [[Regression]], [[Classification]], [[Linear Regression]], [[Logistic Regression]], [[Loss Function]], [[Gradient Descent]].
- Добавлены evaluation и metrics: [[Train Test Split]], [[Cross Validation]], [[Accuracy Precision Recall и F1]], [[Confusion Matrix]].
- Добавлены model selection и tree-based algorithms: [[Parameters и Hyperparameters]], [[Grid Search]], [[Decision Tree]], [[Random Forest]], [[XGBoost]].

### 🧠 Уровень понимания

- Закреплены Regression vs Classification, Train/Test Split, Loss и Gradient Descent, Overfitting/Underfitting, metrics и Feature Scaling.
- На повторение: [[Parameters и Hyperparameters]], реальные примеры [[Data Leakage]], практика pandas/sklearn.

### Следующий шаг

- После Neural Networks вернуться к практическому ML: pandas → sklearn → train/test split → Logistic Regression → Decision Tree → Random Forest → XGBoost.

## 2026-06-26 (KNOWLEDGE_EXPORT: Математика для Machine Learning)

### ✅ Импортировано

- Создан подраздел [[Machine Learning/Mathematics/README|Математика для Machine Learning]].
- Добавлены темы линейной алгебры: [[Вектор]], [[Размерность вектора]], [[Матрица]], [[Матричное умножение]], [[Cosine Similarity]].
- Добавлены темы анализа и оптимизации: [[Производная]], [[Частная производная]], [[Градиент]], [[Machine Learning/Gradient Descent|Gradient Descent]], [[Neural Networks/Learning Rate|Learning Rate]].
- Добавлены темы вероятности и информации: [[Вероятность]], [[Распределения и Mean]], [[Entropy]].

### 🧠 Уровень понимания

- Математическая база достаточна для продолжения Neural Networks и PyTorch.
- Слабые места: интуиция производной, различие Loss и Gradient, различие вероятности и распределения.

### Следующий шаг

- Закреплять производные и градиенты на практических примерах в коде PyTorch.

## 2026-06-26 (KNOWLEDGE_EXPORT: Neural Networks — Dataset и Inference)

### ✅ Импортировано

- Созданы и обновлены темы: [[Neural Networks/Dataset для обучения модели|Dataset]], [[Train Set]], [[Neural Networks/Validation Set|Validation Set]], [[Test Set]], [[Inference]].
- Добавлены PyTorch-preview темы: [[model.train() и model.eval()]], [[torch.no_grad()]].
- Созданы мосты к PyTorch: [[PyTorch/nn.Module|nn.Module]], [[PyTorch/torch.optim|torch.optim]], [[PyTorch/model.eval()|model.eval()]].
- Создано оглавление модуля: [[Neural Networks/README|Neural Networks README]].

### ✅ Итог модуля

- Модуль [[Neural Networks/Index|Neural Networks]] завершен.
- Итоговая проверка пройдена.
- Общий уровень понимания: высокий.
- Основные слабые места: [[Adam]], [[Chain Rule]], отличие [[Batch Normalization]] от [[Machine Learning/Feature Scaling|Feature Scaling]].

### Следующий шаг

- Активировать модуль [[PyTorch/Index|PyTorch]] и увидеть в коде: [[PyTorch/Tensor|Tensor]], [[PyTorch/nn.Module|nn.Module]], [[PyTorch/Autograd|Autograd]], `loss.backward()`, [[PyTorch/torch.optim|optimizer.step()]].

## 2026-06-26 (KNOWLEDGE_EXPORT: Neural Networks — Optimizers и Regularization)

### ✅ Импортировано

- Обновлены stub-заметки [[Optimizer]], [[Batch]], [[Epoch]] и [[Adam]].
- Созданы темы оптимизации: [[Batch Gradient Descent]], [[SGD]], [[Mini-Batch Gradient Descent]], [[Momentum]].
- Созданы темы регуляризации: [[Machine Learning/Overfitting|Overfitting]], [[Dropout]], [[Batch Normalization]].
- Добавлены stub-связи для [[Train Set]], [[Neural Networks/Validation Set|Validation]], [[Test Set]], [[Scaling]], [[Train Validation Test]] и [[Regularization]].

### 🧠 Уровень понимания

- Закреплены различия Optimizer / Backpropagation, Batch / Epoch, Mini-Batch как стандарт обучения.
- На повторение: математика [[Adam]], внутреннее устройство [[Momentum]], отличие [[Batch Normalization]] от [[Machine Learning/Feature Scaling|Feature Scaling]].

### Следующий шаг

- Перейти к [[Train Validation Test]], Dataset и [[Inference]].

## 2026-06-26 (KNOWLEDGE_EXPORT: Neural Networks — Forward Pass и Learning)

### ✅ Импортировано

- Обновлены заметки [[Forward Pass]], [[Backpropagation]], [[Gradient]], [[Vanishing Gradient]] и [[Machine Learning/Gradient Descent|Gradient Descent]].
- Созданы новые темы: [[Hierarchical Feature Learning]], [[Loss]], [[Derivative]], [[Chain Rule]], [[Learning Rate]].
- Добавлены stub-связи для [[Layer]], [[Deep Learning]] и [[Adam]].

### 🧠 Уровень понимания

- Закреплена цепочка: [[Forward Pass]] → [[Loss]] → [[Backpropagation]] → [[Gradient]] → [[Optimizer]] → Update.
- На повторение: [[Chain Rule]], порядок этапов обучения, различие Gradient / Backpropagation / Optimizer.

### Следующий шаг

- Перейти к [[Optimizer]], [[Batch]], [[Epoch]] и организации цикла обучения.

## 2026-06-26 (KNOWLEDGE_EXPORT: Neural Networks)

### ✅ Импортировано

- Обновлены ключевые заметки: [[Weights]], [[Bias]], [[Perceptron]], [[Activation Function]].
- Созданы новые заметки по fundamentals и activation functions: [[Feature]], [[Model]], [[Score]], [[Sigmoid]], [[Tanh]], [[ReLU]], [[Dead Neuron]], [[Leaky ReLU]], [[Softmax]].
- Добавлены stub-заметки для связанных тем: [[Gradient]], [[Optimizer]], [[Forward Pass]], [[Inference]], [[Logits]], [[Output]], [[Vanishing Gradient]].

### 🧠 Уровень понимания

- Закреплены Feature, Weight, Bias, Score, Output и назначение функций активации.
- Особое внимание для повторения: место [[Softmax]] в пайплайне, различие [[Score]] и [[Output]], отличие [[Sigmoid]], [[Tanh]], [[ReLU]] и [[Softmax]].

### Следующий шаг

- Перейти к [[Forward Pass]] и процессу обучения модели.

## 2026-06-26 (KNOWLEDGE_EXPORT: LangGraph)

### ✅ Импортировано

- Обновлены ключевые заметки LangGraph: [[State]], [[Node]], [[Edge]], [[Conditional Edge]], [[Router]], [[Tool Node]].
- Созданы новые концепции по LangGraph agent architecture и runtime.
- Добавлены stub-заметки для связанных терминов.
- Добавлен раздел практики LangGraph из 7 мини-проектов.

### 🧠 Уровень понимания

- Понимание State, Node, Edge, Router, Checkpoint, Memory, Tool Node, Planner/Executor и Multi-Agent архитектуры отмечено как learned.
- Слабые места: add_conditional_edges, Router без подсказки, несколько Tool с последовательными Router.

### 🔁 Повторить

- [[State Update]]
- [[Router]]
- [[Conditional Edge]]
- [[Практика LangGraph 07 - WhatToCook]]

## 2026-06-26 (Сеанс 3: Заполнение структуры)

### ✅ Создано

**Neural Networks (5 концепций):**
- ✅ [[Perceptron]] — stub заметка
- ✅ [[Weights]] — stub заметка
- ✅ [[Bias]] — stub заметка
- ✅ [[Activation Function]] — stub заметка
- ✅ [[Backpropagation]] — stub заметка

**PyTorch (8 концепций):**
- ✅ [[Tensor]] — stub заметка
- ✅ [[Shape]] — stub заметка
- ✅ [[Broadcasting]] — stub заметка
- ✅ [[View]] — stub заметка
- ✅ [[Reshape]] — stub заметка
- ✅ [[Unsqueeze]] — stub заметка
- ✅ [[Squeeze]] — stub заметка
- ✅ [[Autograd]] — stub заметка

**LangGraph (6 концепций):**
- ✅ [[State]] — stub заметка
- ✅ [[Node]] — stub заметка
- ✅ [[Edge]] — stub заметка
- ✅ [[Router]] — stub заметка
- ✅ [[Conditional Edge]] — stub заметка
- ✅ [[Tool Node]] — stub заметка

**AI Engineering (5 концепций):**
- ✅ [[RAG]] — stub заметка
- ✅ [[Embeddings]] — stub заметка
- ✅ [[Vector Database]] — stub заметка
- ✅ [[LLM]] — stub заметка
- ✅ [[AI Agent]] — stub заметка

**Обновлены Index файлы:**
- ✅ [[Indexes/PyTorch Index|PyTorch Index]] — добавлены ссылки на 8 концепций
- ✅ [[Indexes/LangGraph Index|LangGraph Index]] — добавлены ссылки на 6 концепций
- ✅ [[Indexes/AI Engineering Index|AI Engineering Index]] — создан новый Index для 5 концепций

## 2026-06-26 (Сеанс 2: Knowledge Sync Feature Scaling)

### ✅ Создано

**Knowledge Sync: Feature Scaling:**
- ✅ [[Feature Scaling]] — полная концепция (confidence: 80%, status: learned)
- ✅ [[Machine Learning/Normalization|Normalization]] — stub заметка
- ✅ [[Machine Learning/Feature Standardization|Standardization]] — stub заметка
- ✅ [[Gradient Descent]] — stub заметка
- ✅ [[KNN]] — stub заметка
- ✅ [[SVM]] — stub заметка
- ✅ [[Linear Regression]] — stub заметка
- ✅ [[Logistic Regression]] — stub заметка
- ✅ [[Decision Tree]] — stub заметка
- ✅ [[Random Forest]] — stub заметка
- ✅ [[XGBoost]] — stub заметка
- ✅ [[Neural Networks]] (Machine Learning) — stub заметка

## 2026-06-26 (Сеанс 1: Инфраструктура)

### ✅ Создано

**Инфраструктура:**
- Структура Vault
- Правила работы (AGENTS.md)
- Базовые папки и файлы
- Шаблоны для заметок (Concept, Review, Sync Package)
- Dashboard и индексы

### 📚 В процессе

### 🎯 Планы на будущее
- Разработать stub заметки в полноценные концепции
- Добавить практические примеры для каждой темы
- Провести проверку (review) изученных концепций

---

## Статистика

| Метрика | Значение |
|---------|----------|
| Всего заметок | 37 |
| Изучено тем | 1 |
| Draft | 36 |
| Learning | 0 |
| Needs Review | 0 |
| Learned | 1 |
| Avg Confidence | 0.02 |

**По доменам:**
- Python Backend: 12 концепций (draft)
- Machine Learning: 12 концепций (1 learned, 11 draft)
- Neural Networks: 5 концепций (draft)
- PyTorch: 8 концепций (draft)
- LangGraph: 6 концепций (draft)
- AI Engineering: 5 концепций (draft)

---

**Форма записи:**
```
## ДАТА

### ✅ Создано
- Новая тема
- Добавлено в индекс

### 📚 В процессе
- Тема 1 (XX%)
- Тема 2 (XX%)

### 🎯 Планы
- Следующая тема
```
