---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - neural-networks
  - pytorch
  - architecture
confidence: 0.9
difficulty: medium
---

# Output

## Простое объяснение

Output — это ответ модели. Размер последнего слоя определяется тем, сколько выходных значений нужно для задачи.

## Зачем это нужно

Если неправильно выбрать размер последнего слоя, модель будет возвращать ответ неправильной формы и плохо сочетаться с функцией потерь.

## Как это работает

- Regression -> обычно 1 выход.
- Binary Classification -> чаще 1 выход.
- Multi-class Classification -> количество выходов равно количеству классов.
- Multi-label Classification -> по одному выходу на каждый независимый класс.

Сначала определяется, какой ответ должна вернуть модель, затем выбирается `out_features` последнего [[PyTorch/nn.Linear|nn.Linear]].

## Пример

```text
regression:
output: 1

multiclass:
output: 10
```

## Типичные ошибки

- Считать число выходов количеством исходных признаков.
- Не связывать последний слой с типом задачи.
- Выбирать output size отдельно от функции потерь.

## Вопросы для проверки

- Почему размер последнего слоя зависит от задачи?
- Чем отличается Regression от Classification?
- Как определить тип задачи по последнему слою?

## Следующие темы

- [[Machine Learning/Loss Function|Loss Function]]

## Связанные темы

- [[Feature]] · [[Activation Function]] · [[Model]] · [[PyTorch/nn.Linear|nn.Linear]] · [[Machine Learning/Classification|Classification]] · [[Machine Learning/Regression|Regression]]
