---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-07-11
tags: [machine-learning, evaluation, overfitting, generalization, bias, neural-networks]
aliases: [Переобучение, Model Overfitting, Переобучение модели]
confidence: 0.95
difficulty: beginner
---

# Overfitting

Область: [[Machine Learning/Machine Learning|Machine Learning]]

## Академическое определение

Overfitting — состояние модели, при котором она чрезмерно подстраивается под обучающую выборку, включая её шум и случайные особенности, и поэтому хуже обобщает на новые данные.

## Инженерное назначение

Концепция используется для диагностики разрыва между train quality и качеством на validation/test data, выбора сложности модели и применения regularization.

## Причина существования

Минимизация train loss сама по себе не гарантирует полезную модель. Без контроля обобщения можно получить почти идеальные train metrics и плохое качество в production.

## Простое объяснение

Модель выучила ответы и запомнила train-данные вместе с шумом, но не научилась находить общую закономерность для новых примеров.

## Как это работает

Признаки:

- низкая потеря на train;
- заметно более высокая потеря на validation или test;
- модель слишком сложная;
- мало данных для обучения.

Способы уменьшения:

- регуляризация;
- [[Neural Networks/Dropout|Dropout]];
- early stopping;
- больше данных;
- менее сложная модель.

## Пример

```python
# Признак overfitting
print(f"Train loss: {train_loss}")       # низкая
print(f"Validation loss: {val_loss}")    # высокая
```

Для нейросети возможна ситуация: `Train Accuracy = 99%`, а `Test Accuracy = 72%`.

## Типичные ошибки

- Использовать только train-метрики.
- Не проверять модель на [[Neural Networks/Validation Set|Validation Set]] и [[Neural Networks/Test Set|Test Set]].
- Брать слишком большую модель.
- Слишком долго обучать модель.
- Считать, что высокая Accuracy на train всегда означает хорошую модель.

## Связанные темы

[[Machine Learning/Underfitting|Underfitting]] · [[Machine Learning/Train Test Split|Train Test Split]] · [[Machine Learning/Loss Function|Loss Function]] · [[Machine Learning/Cross Validation|Cross Validation]] · [[Neural Networks/Dropout|Dropout]] · [[Neural Networks/Validation Set|Validation Set]] · [[Neural Networks/Test Set|Test Set]]

## Вопросы для проверки

- Как по train и validation metrics распознать Overfitting?
- Почему низкий train loss не гарантирует хорошее обобщение?
- Какие методы помогают уменьшить Overfitting?

## Следующие темы

[[Machine Learning/Underfitting|Underfitting]] · [[Neural Networks/Dropout|Dropout]] · [[Neural Networks/Regularization|Regularization]]
