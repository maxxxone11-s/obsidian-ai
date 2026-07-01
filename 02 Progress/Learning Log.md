---
type: dashboard
tags:
  - dashboard
  - system
created: 2026-06-26
updated: 2026-06-30
---

# 📊 Журнал прогресса обучения

## 2026-07-01 (KNOWLEDGE_EXPORT sync: Statistics Foundations for Machine Learning)

### ✅ Синхронизировано

- Создана новая Knowledge Area [[Statistics/Index|Statistics]] по явному подтверждению пользователя.
- Модуль синхронизирован в `Statistics`, не в `Math Statistic`.
- Созданы concept-заметки: [[Statistics/Mean|Mean]], [[Statistics/Variance|Variance]], [[Statistics/Причина использования квадратов в статистике|Причина использования квадратов в статистике]], [[Statistics/Standard Deviation|Standard Deviation]], [[Statistics/Min-Max Normalization|Min-Max Normalization]], [[Statistics/Standardization|Standardization]], [[Statistics/Z-score|Z-score]], [[Statistics/Normal Distribution|Normal Distribution]], [[Statistics/Связь основных статистических понятий|Связь основных статистических понятий]].
- Созданы обзорные индексы: [[Statistics/Index|Statistics Index]] и [[Indexes/Statistics Index|Statistics Index]].
- Связи проставлены на существующие темы [[Machine Learning/Feature Scaling|Feature Scaling]], [[Machine Learning/Normalization|Normalization]], [[Machine Learning/Standardization|Standardization]], [[Machine Learning/Mathematics/MSE|MSE]] и [[Transformers/LayerNorm|LayerNorm]].

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
- Обновлены существующие концепции: [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]], [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]], [[PyTorch/train.py как центр обучения|train.py как центр обучения]], [[PyTorch/Dataset|Dataset]], [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]], [[PyTorch/Separation of Concerns|Separation of Concerns]], [[Neural Networks/Model|Model]].
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
- Обновлены существующие концепции: [[PyTorch/Чтение архитектуры PyTorch-проектов|Чтение архитектуры PyTorch-проектов]], [[PyTorch/nn.Module|nn.Module]], [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]], [[PyTorch/Dataset|Dataset]], [[PyTorch/DataLoader|DataLoader]], [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]].
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
- Обновлены и выделены отдельные концепции: [[Machine Learning/Normalization|Normalization]], [[Machine Learning/Standardization|Standardization]], [[Machine Learning/Fit Transform и Data Leakage|Fit Transform и Data Leakage]], [[Machine Learning/Scaling и Gradient Descent|Scaling и Gradient Descent]], [[Machine Learning/Scaling для KNN и SVM|Scaling для KNN и SVM]], [[Machine Learning/Scaling и Tree-Based Models|Scaling и Tree-Based Models]].
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
- Созданы stub-заметки: [[PyTorch/Tensors/Tensor Operations|Tensor Operations]], [[PyTorch/Dataset|Dataset]], [[PyTorch/DataLoader|DataLoader]].

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

- Созданы и обновлены темы: [[Dataset]], [[Train Set]], [[Validation|Validation Set]], [[Test Set]], [[Inference]].
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
- Созданы темы регуляризации: [[Overfitting]], [[Dropout]], [[Batch Normalization]].
- Добавлены stub-связи для [[Train Set]], [[Validation]], [[Test Set]], [[Scaling]], [[Train Validation Test]] и [[Regularization]].

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
- ✅ [[Normalization]] — stub заметка
- ✅ [[Standardization]] — stub заметка
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
