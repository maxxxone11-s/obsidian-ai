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
