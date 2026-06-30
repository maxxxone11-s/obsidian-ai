---
type: concept
area: PyTorch
status: learned
created: 2026-06-30
updated: 2026-06-30
tags:
  - pytorch
  - inference
  - ml-engineering
confidence: 0.99
difficulty: medium
---

# predict.py

## Простое объяснение

`predict.py` отвечает за использование уже обученной модели.

## Зачем это нужно

Так обучение отделяется от эксплуатации модели: `train.py` обучает, а `predict.py` получает предсказания.

## Как это работает

```text
загрузка модели
↓
подготовка изображения
↓
model.eval()
↓
torch.no_grad()
↓
prediction
```

## Пример

```python
prediction = predict("cat.jpg")
```

## Типичные ошибки

- Использовать `train.py` для inference.
- Смешивать код обучения и код предсказания.

## Вопросы для проверки

- Почему `predict.py` существует отдельно?
- Какие этапы входят в prediction script?

## Следующие темы

- [[Inference Pipeline]]

## Связанные темы

- [[load_model()]] · [[preprocess_image()]] · [[predict()]] · [[Neural Networks/Inference|Inference]]
