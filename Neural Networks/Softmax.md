---
type: concept
area: Machine Learning
status: learned
created: 2026-06-26
updated: 2026-06-30
tags:
  - machine-learning
  - mathematics
  - probability
  - neural-networks
  - activation-functions
confidence: 0.95
difficulty: medium
---

# Softmax

## Кратко

Softmax преобразует logits в вероятности.

## Простое объяснение

Softmax сравнивает сразу все ответы модели и распределяет вероятность между ними так, чтобы сумма вероятностей была равна 1.

## Зачем это нужно

Используется в многоклассовой классификации, inference pipeline и современных LLM.

## Как это работает

Softmax принимает весь вектор [[Logits]], усиливает большие значения и нормирует результат так, чтобы получить распределение вероятностей.

В PyTorch при batch outputs `softmax(dim=1)` означает: применить Softmax по классам для каждого объекта batch отдельно.

## Пример

```text
logits: [8, 2, 5]
probabilities: [94%, 1%, 5%]
```

```python
torch.softmax(outputs, dim=1)
```

## Типичные ошибки

- Путать Softmax и Sigmoid.
- Думать, что Softmax работает с одним Score.
- Использовать неверную размерность `dim`.

## Вопросы для проверки

- Почему Softmax работает сразу со всем вектором?
- Чем Softmax отличается от Sigmoid?
- Что делает Softmax?
- Почему при batch обычно используется `dim=1`?

## Следующие темы

- [[Forward Pass]]
- [[Entropy]]
- [[PyTorch/top_k|top_k]]

## Связанные темы

- [[Logits]] · [[Sigmoid]] · [[Output]] · [[Entropy]] · [[PyTorch/Inference Pipeline|Inference Pipeline]]
