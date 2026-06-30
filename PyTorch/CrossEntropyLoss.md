---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - loss
  - classification
confidence: 0.99
difficulty: hard
---

# CrossEntropyLoss

## Простое объяснение

Модель выдает оценки классов, то есть [[Neural Networks/Logits|logits]]. `CrossEntropyLoss` внутри превращает их в логарифмическое распределение вероятностей и проверяет, насколько высока оценка правильного класса.

## Зачем это нужно

`CrossEntropyLoss` — стандартная функция потерь для задач многоклассовой классификации в PyTorch.

## Как это работает

На вход подаются:

- `outputs` — logits модели;
- `labels` — индексы правильных классов.

Внутри происходит:

```text
logits
↓
LogSoftmax
↓
вероятности в логарифмической форме
↓
NLLLoss
↓
ошибка только по правильному классу
```

Чем выше вероятность правильного класса, тем меньше loss.

## Пример

```text
outputs = [2.1, 0.5, 4.8]
label = 2

после внутреннего Softmax:
[0.06, 0.01, 0.93]

loss считается по вероятности класса 2
```

## Типичные ошибки

- Добавлять Softmax перед `CrossEntropyLoss`.
- Передавать вероятности вместо logits.
- Думать, что `CrossEntropyLoss` сравнивает числа вычитанием как `MSELoss`.

## Вопросы для проверки

- Что получает `CrossEntropyLoss` на вход?
- Почему модель возвращает logits?
- Почему Softmax не нужен внутри модели?
- По какому классу считается ошибка?

## Следующие темы

- Binary Cross Entropy
- Multi-label Classification

## Связанные темы

- [[Machine Learning/Mathematics/Cross Entropy|Cross Entropy]] · [[Neural Networks/Logits|Logits]] · [[Neural Networks/Softmax|Softmax]] · [[Machine Learning/Classification|Classification]] · [[Machine Learning/Loss Function|Loss Function]]
