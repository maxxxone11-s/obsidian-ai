---
type: concept
area: ml-basics
status: draft
created: 2026-06-26
updated: 2026-06-26
tags: [train, test, split, data]
confidence: 0
---

# Train/Test Split

Разделение данных на обучающий и тестовый наборы.

## Простое объяснение

Train/Test Split делит данные на две части: одну для обучения модели, другую для проверки.

## Интуитивное объяснение

Как учеба и экзамен — готовитесь на одних материалах, проверяетесь на других.

## Зачем это нужно

- Проверка обобщающей способности модели
- Избежание переобучения
- Объективная оценка качества

## Как это работает

### Классический подход
- Обычно 80% train, 20% test
- Иногда добавляют validation set

## Пример

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

## Типичные ошибки

- Утечка данных из test в train
- Неправильный порядок (масштабировать после split)
- Забывают про random_state для воспроизводимости

## Связанные темы

- [[Feature Scaling]] — масштабировать после split!
- [[Overfitting]] — проверяют с test set
- [[Loss Function]] — вычисляют на обоих наборах

---

**Дата создания:** 2026-06-26
**Статус:** draft — требует разработки
