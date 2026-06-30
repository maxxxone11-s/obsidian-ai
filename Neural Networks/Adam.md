---
type: concept
area: Neural Networks
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - neural-networks
  - optimizers
confidence: 0.96
difficulty: hard
---

# Adam

## Кратко

Adam объединяет Momentum и адаптивный Learning Rate.

## Простое объяснение

Adam получает список параметров модели и после backward изменяет их значения. Он учитывает историю градиентов и подбирает адаптивный шаг для разных параметров.

## Зачем это нужно

Adam — один из самых распространенных оптимизаторов в современных ML-проектах.

## Как это работает

```text
model.parameters()
↓
список weight и bias
↓
loss.backward()
↓
появляются .grad
↓
optimizer.step()
↓
параметры обновляются
```

Adam хранит историю градиентов и использует ее для адаптации шага обновления каждого параметра.

## Пример

```python
optimizer = torch.optim.Adam(model.parameters(), lr=0.001)
```

## Типичные ошибки

- Думать, что Adam вычисляет Gradient.
- Не понимать, откуда берется индивидуальный Learning Rate.
- Думать, что Adam обновляет модель самостоятельно без `backward()`.
- Считать, что Adam получает всю модель вместо параметров.
- Считать, что Adam использует одинаковый шаг для всех параметров.

## Вопросы для проверки

- Почему Adam лучше обычного SGD?
- Что он хранит кроме Gradient?
- Что получает Adam при создании?
- Что происходит при `optimizer.step()`?
- Почему Adam считается адаптивным?

## Следующие темы

- [[PyTorch/model.parameters()|model.parameters()]]

## Связанные темы

- [[Forward Pass]] · [[Backpropagation]] · [[Gradient]] · [[Momentum]] · [[Learning Rate]] · [[Optimizer]] · [[PyTorch/torch.optim|torch.optim]] · [[PyTorch/model.parameters()|model.parameters()]]
