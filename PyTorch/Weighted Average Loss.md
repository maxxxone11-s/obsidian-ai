---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - loss
  - metrics
confidence: 0.98
difficulty: medium
---

# Weighted Average Loss

## Простое объяснение

Средний loss нужно считать с учетом размера каждого batch.

## Зачем это нужно

Маленькие batch не должны влиять на среднее так же сильно, как большие. Взвешенное среднее дает корректную оценку качества обучения.

## Как это работает

```text
sum(loss_i * batch_size_i) / sum(batch_size_i)
```

## Пример

```python
np.sum(np.multiply(losses, nums)) / np.sum(nums)
```

## Типичные ошибки

- Усреднять loss без учета размера batch.
- Считать последний неполный batch равным по весу полному batch.

## Вопросы для проверки

- Почему используется взвешенное среднее?
- Что будет, если batch sizes различаются?

## Следующие темы

- Metrics

## Связанные темы

- [[loss.item()]] · [[PyTorch Training Loop]] · [[Neural Networks/Batch|Batch]]
