---
type: index
area: PyTorch
created: 2026-06-26
updated: 2026-06-30
tags:
  - index
  - system
  - pytorch
---

# PyTorch Index

Указатель всех концепций, связанных с PyTorch фреймворком.

## Tensor Fundamentals

- [[PyTorch/Tensors/Index|PyTorch Tensor Fundamentals Index]]
- [[PyTorch/Tensor|Tensor]] — основной объект PyTorch
- [[PyTorch/Tensors/Tensor Dimensions (ndim)|Tensor Dimensions (ndim)]] — количество осей
- [[PyTorch/Shape|Tensor Shape]] — форма и структура Tensor
- [[PyTorch/Tensors/Tensor Creation|Tensor Creation]] — создание Tensor
- [[PyTorch/Tensors/Tensor Dtype|Tensor Dtype]] — типы данных
- [[PyTorch/Tensors/Tensor Indexing and Slicing|Tensor Indexing and Slicing]] — индексация и срезы
- [[PyTorch/Reshape|Reshape]] — изменение формы
- [[PyTorch/View|View]] — изменение формы без копирования
- [[PyTorch/Unsqueeze|Unsqueeze]] — добавление размерности
- [[PyTorch/Squeeze|Squeeze]] — удаление размерности
- [[PyTorch/Broadcasting|Broadcasting]] — операции между совместимыми Tensor
- [[PyTorch/Tensors/Tensor Operations|Tensor Operations]] — следующий stub-блок
- [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch (matmul)]] — `*` vs `@`

## PyTorch Foundations II

- [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch (matmul)]] — связь tensor operations и персептрона
- [[PyTorch/nn.Linear|nn.Linear]] — Linear Layer как `x @ w + b`
- [[PyTorch/Autograd|Autograd]] — автоматическое вычисление производных
- [[PyTorch/PyTorch Training Loop|PyTorch Training Loop]] — полный цикл обучения
- [[Machine Learning/Mathematics/Производная|Производная]] — базовые производные для AI
- [[Machine Learning/Gradient Descent|Gradient Descent]] — обновление весов
- [[Machine Learning/Loss Function|Loss Function]] — откуда появляется Loss

## PyTorch Foundations III

- [[Neural Networks/Train Validation Test|Train Validation Test]] — роли train, validation и test
- [[PyTorch/nn.Module|nn.Module]] — `__init__`, `forward` и вызов `model(x)`
- [[PyTorch/Многослойная нейронная сеть|Многослойная нейронная сеть]] — слои работают с выходами предыдущих слоев
- [[Neural Networks/ReLU|ReLU]] — нелинейность между Linear-слоями
- [[PyTorch/Анализ архитектуры модели по слоям|Анализ архитектуры модели по слоям]] — shape и совместимость слоев
- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] — режимы модели
- [[PyTorch/model.eval()|model.eval()]] — PyTorch-режим inference
- [[Neural Networks/Output|Output]] — размер последнего слоя по задаче
- [[PyTorch/Чтение архитектуры PyTorch-проектов|Чтение архитектуры PyTorch-проектов]] — чтение параметров архитектуры

## GitHub Projects & ML Architecture

- [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]] — порядок чтения ML-репозитория
- [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]] — структура проекта
- [[PyTorch/model.py как отдельная ответственность|model.py как отдельная ответственность]] — описание архитектуры модели
- [[PyTorch/train.py как центр обучения|train.py как центр обучения]] — соединение Dataset, Model, Loss и Optimizer
- [[PyTorch/config.py|config.py]] — настройки проекта
- [[PyTorch/Separation of Concerns|Separation of Concerns]] — один файл, одна ответственность
- [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]] — контракт данных между компонентами
- [[Machine Learning/Parameters и Hyperparameters|Parameters и Hyperparameters]] — гиперпараметры vs параметры датасета

## Loss, Optimization & Autograd

- [[PyTorch/CrossEntropyLoss|CrossEntropyLoss]] — loss для multi-class classification
- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] — математическая идея Cross Entropy
- [[Neural Networks/Logits|Logits]] — сырые выходы модели
- [[Neural Networks/Adam|Adam]] — адаптивный optimizer
- [[PyTorch/model.parameters()|model.parameters()]] — trainable параметры модели
- [[PyTorch/Autograd|Autograd]] — computation graph и `backward()`
- [[Neural Networks/torch.no_grad()|torch.no_grad()]] — inference без computation graph
- [[Neural Networks/model.train() и model.eval()|model.train() и model.eval()]] — режимы модели
- [[PyTorch/DataLoader|DataLoader]] — batch loading под капотом

## GitHub File Analysis & Inference Pipeline

- [[PyTorch/model.py как отдельная ответственность|model.py как отдельная ответственность]] — review файла модели
- [[PyTorch/train.py как центр обучения|train.py как центр обучения]] — review training script
- [[PyTorch/train_utils.py|train_utils.py]] — helper-функции обучения
- [[PyTorch/predict.py|predict.py]] — inference script
- [[PyTorch/Inference Pipeline|Inference Pipeline]] — полный prediction pipeline
- [[PyTorch/load_model()|load_model()]] — загрузка модели
- [[PyTorch/preprocess_image()|preprocess_image()]] — подготовка изображения
- [[PyTorch/predict()|predict()]] — функция предсказания
- [[PyTorch/top_k|top_k]] — несколько лучших классов
- [[PyTorch/Unsqueeze|Unsqueeze]] — `unsqueeze(0)` для batch dimension
- [[PyTorch/loss.item()|loss.item()]] — Tensor loss в Python number
- [[PyTorch/Weighted Average Loss|Weighted Average Loss]] — средний loss с учетом batch size
- [[PyTorch/Tuple Unpacking|Tuple Unpacking]] — распаковка нескольких return values

## Engineering Mindset & GitHub Project Analysis

- [[PyTorch/Reading GitHub ML Projects|Reading GitHub ML Projects]] — чтение репозитория через архитектуру
- [[PyTorch/Как анализировать неизвестный код|Как анализировать неизвестный код]] — вопросы к незнакомому файлу
- [[PyTorch/Архитектура ML-проекта|Архитектура ML-проекта]] — понимание проекта по структуре файлов
- [[PyTorch/Модель как универсальная функция|Модель как универсальная функция]] — модель как `features -> prediction`
- [[PyTorch/train.py как центр обучения|train.py как центр обучения]] — train loop не зависит от источника данных
- [[PyTorch/Dataset|Dataset]] — replaceable Dataset через стабильный интерфейс
- [[PyTorch/Интерфейс Dataset DataLoader Model|Интерфейс Dataset DataLoader Model]] — контракт между компонентами
- [[PyTorch/Интерфейс важнее реализации|Интерфейс важнее реализации]] — interface over implementation
- [[PyTorch/Повторение терминов PyTorch Foundations|Повторение терминов PyTorch Foundations]] — связанный словарь модуля

## Основы PyTorch

- [[PyTorch/Autograd|Autograd]] — автоматическое дифференцирование
- [[PyTorch/nn.Module|nn.Module]] — базовый класс модели
- [[PyTorch/nn.Linear|nn.Linear]] — линейный слой
- [[PyTorch/torch.optim|torch.optim]] — оптимизаторы
- [[PyTorch/model.eval()|model.eval()]] — режим inference
- [[PyTorch/Dataset|Dataset]] — источник данных
- [[PyTorch/DataLoader|DataLoader]] — batch-загрузка данных

## Модели и слои

- Linear слой
- Convolutional слой
- Recurrent слой
- Attention слой
- Custom layers

## Обучение

- DataLoader
- Оптимизаторы (SGD, Adam, RMSprop)
- Функции потерь (CrossEntropy, MSE, BCE)
- Training loop
- Validation loop

## Архитектуры

- MLP (Multi-Layer Perceptron)
- CNN (Convolutional Neural Networks)
- RNN (Recurrent Neural Networks)
- LSTM и GRU
- Transformers
- Vision Transformers

## Практика

- Предварительно обученные модели (pretrained models)
- Fine-tuning
- Transfer Learning
- Сохранение и загрузка моделей

## Продвинутые темы

- Distributed training
- Mixed precision training (AMP)
- Quantization
- Pruning

---

**Обновлено:** 2026-06-30
