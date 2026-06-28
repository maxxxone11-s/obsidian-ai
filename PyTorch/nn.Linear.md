---
type: concept
area: PyTorch
status: learned
created: 2026-06-28
updated: 2026-06-28
tags:
  - pytorch
  - neural-networks
  - linear-layer
  - layer
confidence: 0.95
difficulty: easy
---

# nn.Linear

## Кратко

Изучено устройство Linear Layer и его связь с формулой персептрона.

## Простое объяснение

`nn.Linear` автоматически создаёт веса и смещение.

## Зачем это нужно

Практически каждая современная нейросеть использует Linear Layer.

## Как это работает

`nn.Linear` — удобная оболочка над формулой:

```text
x @ w + b
```

Ключевые идеи:

- `nn.Linear(in_features, out_features)`;
- автоматически создаёт `weight`;
- автоматически создаёт `bias`;
- веса инициализируются случайно;
- каждый выходной нейрон имеет собственные веса.

Linear Layer — это множество персептронов.

## Пример

```python
import torch
from torch import nn

layer = nn.Linear(3, 1)
x = torch.tensor([ [1.0, 2.0, 3.0] ])

output = layer(x)
print(output)
```

## Типичные ошибки

- Путать, что означают `3` и `1` в `nn.Linear(3, 1)`.
- Считать, что PyTorch создаёт признаки, а не веса.

## Вопросы для проверки

- Что означает `nn.Linear(3, 1)`?
- Что автоматически создаётся?
- Почему веса случайные?
- Что происходит внутри `layer(x)`?

## Следующие темы

- [[Autograd]]

## Связанные темы

- [[Neural Networks/Perceptron|Perceptron]]
- [[Neural Networks/Weights|Weights]]
- [[Neural Networks/Bias|Bias]]
- [[Matrix Multiplication in PyTorch (matmul)]]
- [[nn.Module]]
