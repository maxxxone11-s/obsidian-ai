---
type: index
area: PyTorch
created: 2026-06-26
updated: 2026-06-30
tags:
  - index
  - system
---

# ⚡ PyTorch

## Структура раздела

Фреймворк PyTorch для глубокого обучения.

### Tensor Fundamentals

- [[PyTorch/Tensors/Index|PyTorch Tensor Fundamentals Index]]
- [[Tensor]] — основной объект PyTorch
- [[PyTorch/Tensors/Tensor Dimensions (ndim)|Tensor Dimensions (ndim)]] — количество осей
- [[Shape|Tensor Shape]] — форма и структура Tensor
- [[PyTorch/Tensors/Tensor Creation|Tensor Creation]] — создание Tensor
- [[PyTorch/Tensors/Tensor Dtype|Tensor Dtype]] — типы данных
- [[PyTorch/Tensors/Tensor Indexing and Slicing|Tensor Indexing and Slicing]] — индексация и срезы
- [[Reshape]] — изменение формы
- [[View]] — изменение формы без копирования
- [[Unsqueeze]] — добавление размерности
- [[Squeeze]] — удаление размерности
- [[Broadcasting]] — операции между совместимыми Tensor
- [[Matrix Multiplication in PyTorch (matmul)]] — `*` vs `@`
- [[PyTorch/Tensors/Tensor Operations|Tensor Operations]] — следующий stub-блок

### PyTorch Foundations II

- [[Matrix Multiplication in PyTorch (matmul)]] — матричное умножение в PyTorch
- [[nn.Linear]] — Linear Layer
- [[Autograd]] — автоматическое вычисление производных
- [[PyTorch Training Loop]] — цикл обучения
- [[Machine Learning/Mathematics/Производная|Производная]] — производные для AI
- [[Machine Learning/Gradient Descent|Gradient Descent]] — шаг оптимизации
- [[Machine Learning/Loss Function|Loss Function]] — ошибка модели

### PyTorch Foundations III

- [[Neural Networks/Train Validation Test|Train Validation Test]] — роли train, validation и test
- [[nn.Module]] — архитектура модели через `__init__` и `forward`
- [[Многослойная нейронная сеть]] — последовательное построение признаков
- [[Neural Networks/ReLU|ReLU]] — нелинейность между Linear-слоями
- [[Анализ архитектуры модели по слоям]] — чтение shape по слоям
- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] — режимы обучения и инференса
- [[Neural Networks/Output|Output]] — выбор размера последнего слоя по задаче
- [[Чтение архитектуры PyTorch-проектов]] — чтение реальных моделей

### GitHub Projects & ML Architecture

- [[Reading GitHub ML Projects]] — порядок чтения ML-репозитория
- [[Архитектура ML-проекта]] — структура файлов и поток данных
- [[model.py как отдельная ответственность]] — файл модели
- [[train.py как центр обучения]] — сценарий обучения
- [[config.py]] — настройки проекта
- [[Separation of Concerns]] — разделение ответственности
- [[Интерфейс Dataset DataLoader Model]] — контракт передачи данных
- [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]] — гиперпараметры vs параметры датасета

### Loss, Optimization & Autograd

- [[CrossEntropyLoss]] — PyTorch loss для multi-class classification
- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] — математическая идея loss
- [[Neural Networks/Logits|Logits]] — сырые outputs модели
- [[Neural Networks/Adam|Adam]] — адаптивный optimizer
- [[model.parameters()]] — trainable параметры модели
- [[Autograd]] — computation graph и `backward()`
- [[Neural Networks/torch.no_grad()|torch.no_grad()]] — отключение graph для inference
- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] — режимы модели
- [[DataLoader]] — batch loading под капотом

### GitHub File Analysis & Inference Pipeline

- [[model.py как отдельная ответственность]] — review файла модели
- [[train.py как центр обучения]] — review training script
- [[train_utils.py]] — helper-функции обучения
- [[predict.py]] — inference script
- [[Inference Pipeline]] — полный prediction pipeline
- [[load_model()]] — загрузка архитектуры и весов
- [[preprocess_image()]] — подготовка изображения
- [[predict()]] — функция предсказания
- [[top_k]] — несколько лучших классов
- [[Unsqueeze]] — `unsqueeze(0)` для batch dimension
- [[loss.item()]] — Tensor loss в Python number
- [[Weighted Average Loss]] — средний loss с учетом batch size
- [[Tuple Unpacking]] — распаковка нескольких return values

### Engineering Mindset & GitHub Project Analysis

- [[Reading GitHub ML Projects]] — чтение репозитория через архитектуру
- [[Как анализировать неизвестный код]] — вопросы к незнакомому файлу
- [[Архитектура ML-проекта]] — понимание проекта по структуре файлов
- [[Модель как универсальная функция]] — модель как `features -> prediction`
- [[train.py как центр обучения]] — независимость train loop от источника данных
- [[Dataset]] — replaceable Dataset через стабильный интерфейс
- [[Интерфейс Dataset DataLoader Model]] — контракт между компонентами
- [[Интерфейс важнее реализации]] — interface over implementation
- [[Повторение терминов PyTorch Foundations]] — связанный словарь модуля

### Основы PyTorch
- [[Autograd]] — автоматическое дифференцирование
- Динамические графы вычислений
- [[Dataset]] — источник данных
- [[DataLoader]] — batch-загрузка данных

### Модели и слои
- [[nn.Module]] — базовый класс модели
- [[nn.Linear]] — линейный слой
- Создание собственных слоев
- Sequential vs Custom models

### Обучение
- [[DataLoader]] — загрузка данных
- [[torch.optim]] — оптимизаторы
- Функции потерь
- Процесс обучения (train loop)

### Практика
- Предварительно обученные модели
- Fine-tuning
- Сохранение и загрузка моделей

### Продвинутые темы
- Distributed training
- Mixed precision training
- Quantization

---

**Дата создания:** 2026-06-26
**Обновлено:** 2026-06-30


## Связи с Neural Networks

- [[Tensor]] — данные и параметры
- [[nn.Module]] — реализация [[Neural Networks/Forward Pass|Forward Pass]]
- [[nn.Linear]] — реализация формулы [[Neural Networks/Perceptron|Perceptron]]
- [[Autograd]] — автоматический [[Neural Networks/Gradient|Gradient]]
- [[torch.optim]] — реализация [[Neural Networks/Optimizer|Optimizer]]
- [[model.eval()]] — режим [[Neural Networks/Inference|Inference]]
