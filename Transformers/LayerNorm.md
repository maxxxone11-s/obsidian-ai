---
type: concept
area: Transformers
knowledge_area: Transformers
status: needs_review
created: 2026-06-30
updated: 2026-06-30
tags:
  - transformers
confidence: low
difficulty: hard
aliases:
  - Layer Normalization
---

# LayerNorm

## Кратко

После Residual Connection значения embedding могут постепенно менять масштаб. Чтобы следующий Transformer Block получал данные в стабильном диапазоне, применяется LayerNorm.

## Простое объяснение

LayerNorm стабилизирует значения embedding перед передачей следующему Transformer Block.

## Зачем это нужно

Без понимания статистики невозможно полностью понять механизм LayerNorm, потому что он опирается на среднее значение, дисперсию и стандартное отклонение.

## Как это работает

LayerNorm нормализует embedding после объединения исходного embedding и результата Attention.

```python
x = x + attention(x)
x = layer_norm(x)
```

Полный математический смысл LayerNorm требует понимания:

- среднего значения;
- дисперсии;
- стандартного отклонения.

Эти темы являются предварительным математическим фундаментом и изучаются отдельно.

## Пример

```text
x + Attention(x)
    ↓
LayerNorm
    ↓
следующий Transformer Block
```

## Типичные ошибки

- Считать LayerNorm простым делением на фиксированное число.
- Пытаться изучать LayerNorm без понимания статистики.

## Вопросы для проверки

- Почему LayerNorm выполняется после Residual?
- Какую проблему решает LayerNorm?

## Следующие темы

- Mean
- Variance
- Standard Deviation
- LayerNorm Mathematics

## Связанные темы

- [[Transformer Block]] · [[Residual Connection]] · [[Machine Learning/Normalization|Normalization]]
