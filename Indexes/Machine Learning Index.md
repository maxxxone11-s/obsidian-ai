---
type: index
area: Machine Learning
created: 2026-06-26
updated: 2026-06-27
tags:
  - index
  - system
---

# 🤖 Machine Learning Index

Указатель всех концепций, связанных с машинным обучением.

## Структура

### Основы ML
- Что такое машинное обучение
- Supervised vs Unsupervised learning
- Reinforcement Learning
- Transfer Learning

### Подготовка данных
- Data cleaning
- Feature engineering
- [[Feature Scaling]] — приведение признаков к единому масштабу
- [[Normalization]] — масштабирование к диапазону [0, 1]
- [[Standardization]] — z-score нормализация
- [[Fit Transform и Data Leakage]] — правильный scaling train/test
- [[Scaling и Gradient Descent]] — влияние масштаба на оптимизацию
- [[Scaling для KNN и SVM]] — distance-based модели
- [[Scaling и Tree-Based Models]] — почему деревьям scaling почти не нужен
- Train/Test split

### Библиотеки
- NumPy
- Pandas
- Scikit-learn
- Matplotlib

### Классические алгоритмы
- [[Linear Regression]] — требует масштабирования
- [[Logistic Regression]] — требует масштабирования
- [[KNN]] — требует масштабирования
- [[SVM]] — требует масштабирования
- [[Decision Tree]] — не требует масштабирования
- [[Random Forest]] — не требует масштабирования
- K-Means кластеризация

### Оценка моделей
- Метрики качества (Accuracy, Precision, Recall)
- Cross-validation
- ROC-AUC
- [[XGBoost]] — gradient boosting алгоритм
- Confusion Matrix

### Loss Functions
- [[Loss Function]] — обзор функций потерь
- [[Machine Learning/Mathematics/MSE|MSE]] — средняя квадратичная ошибка
- [[Machine Learning/Mathematics/MAE|MAE]] — средняя абсолютная ошибка
- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] — loss для классификации

### Гиперпараметры
- Grid Search
- Random Search
- Bayesian Optimization


## Machine Learning Fundamentals

### Fundamentals и Data
- [[Что такое Machine Learning]]
- [[Dataset, Features и Labels]]
- [[Data Leakage]]
- [[Связь Machine Learning и Deep Learning]]

### Supervised Learning
- [[Regression]]
- [[Classification]]
- [[Linear Regression]]
- [[Logistic Regression]]

### Optimization и Model Selection
- [[Loss Function]]
- [[Gradient Descent]]
- [[Parameters и Hyperparameters]]
- [[Grid Search]]

### Evaluation
- [[Train Test Split]]
- [[Overfitting]]
- [[Underfitting]]
- [[Cross Validation]]

### Metrics
- [[Accuracy Precision Recall и F1]]
- [[Confusion Matrix]]

### Data Preparation
- [[Feature Engineering]]
- [[Feature Scaling]]
- [[Normalization]]
- [[Standardization]]
- [[Fit Transform и Data Leakage]]
- [[Scaling и Gradient Descent]]
- [[Scaling для KNN и SVM]]
- [[Scaling и Tree-Based Models]]

### Algorithms
- [[Decision Tree]]
- [[Random Forest]]
- [[XGBoost]]

## Математика для Machine Learning

### Линейная алгебра
- [[Machine Learning/Mathematics/Вектор|Вектор]]
- [[Machine Learning/Mathematics/Размерность вектора|Размерность вектора]]
- [[Machine Learning/Mathematics/Длина вектора|Длина вектора]]
- [[Machine Learning/Mathematics/Нормализация вектора|Нормализация вектора]]
- [[Machine Learning/Mathematics/Скалярное произведение|Скалярное произведение]]
- [[Machine Learning/Mathematics/Cosine Similarity|Cosine Similarity]]
- [[Machine Learning/Mathematics/Матрица|Матрица]]
- [[Machine Learning/Mathematics/Операции над матрицами|Операции над матрицами]]
- [[Machine Learning/Mathematics/Матричное умножение|Матричное умножение]]
- [[Machine Learning/Mathematics/Нейрон как скалярное произведение|Нейрон как скалярное произведение]]

### Производные и оптимизация
- [[Machine Learning/Mathematics/Производная|Производная]]
- [[Machine Learning/Mathematics/Частная производная|Частная производная]]
- [[Machine Learning/Mathematics/Градиент|Градиент]]
- [[Machine Learning/Gradient Descent|Gradient Descent]]
- [[Neural Networks/Learning Rate|Learning Rate]]
- [[Machine Learning/Loss Function|Loss Function]]

### Вероятность, статистика и классификация
- [[Machine Learning/Mathematics/Вероятность|Вероятность]]
- [[Machine Learning/Mathematics/Распределения и Mean|Распределения и Mean]]
- [[Neural Networks/Logits|Logits]]
- [[Neural Networks/Softmax|Softmax]]
- [[Machine Learning/Mathematics/Entropy|Entropy]]
- [[Machine Learning/Mathematics/MSE|MSE]]
- [[Machine Learning/Mathematics/MAE|MAE]]
- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]]

---

**Обновлено:** 2026-06-27
