---
type: index
area: PyTorch
created: 2026-06-26
updated: 2026-06-27
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
- [[PyTorch/Tensors/Tensor Operations|Tensor Operations]] — следующий stub-блок

### Основы PyTorch
- [[Autograd]] — автоматическое дифференцирование
- Динамические графы вычислений
- [[Dataset]] — источник данных
- [[DataLoader]] — batch-загрузка данных

### Модели и слои
- [[nn.Module]] — базовый класс модели
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
**Обновлено:** 2026-06-27


## Связи с Neural Networks

- [[Tensor]] — данные и параметры
- [[nn.Module]] — реализация [[Neural Networks/Forward Pass|Forward Pass]]
- [[Autograd]] — автоматический [[Neural Networks/Gradient|Gradient]]
- [[torch.optim]] — реализация [[Neural Networks/Optimizer|Optimizer]]
- [[model.eval()]] — режим [[Neural Networks/Inference|Inference]]
