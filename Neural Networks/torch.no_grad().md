---
type: concept
area: Neural Networks
status: draft
created: 2026-06-26
updated: 2026-06-26
tags:
  - neural-networks
  - pytorch-preview
confidence: 0.7
---

# torch.no_grad()

## Простое объяснение
Если модель не обучается, хранить градиенты больше не нужно.

## Зачем это нужно
Экономит память и ускоряет вычисления.

## Как это работает
Контекст `torch.no_grad()` говорит PyTorch не строить граф вычислений для градиентов. Это полезно на [[Inference]], но вредно во время обучения.

## Пример
```python
with torch.no_grad():
    prediction = model(x)
```

## Типичные ошибки
- Использовать torch.no_grad() во время обучения.

## Вопросы для проверки
- Почему torch.no_grad() ускоряет работу модели?

## Следующие темы
- [[PyTorch/Autograd|PyTorch Autograd]]

## Связанные темы
[[Inference]] · [[Gradient]]
