---
type: concept
area: Transformers
knowledge_area: Transformers
status: learned
created: 2026-06-30
updated: 2026-07-01
tags:
  - transformers
confidence: high
difficulty: hard
aliases:
  - Layer Normalization
  - LayerNorm
---

# LayerNorm

## Академическое определение

LayerNorm — слой нормализации, который стандартизирует признаки каждого embedding независимо от остальных элементов batch.

После [[Residual Connection]] вычисляется нормализованное представление embedding:

```text
LayerNorm(x) = γ * (x - μ) / sqrt(σ² + ε) + β
```

Где:

- `μ` — среднее значение признаков текущего embedding.
- `σ²` — дисперсия признаков текущего embedding.
- `ε` — небольшая константа для предотвращения деления на ноль.
- `γ` — обучаемый коэффициент масштабирования.
- `β` — обучаемый коэффициент смещения.

## Инженерное назначение

LayerNorm приводит каждый embedding к предсказуемому статистическому масштабу перед передачей следующему [[Transformer Block]].

В реальной архитектуре Transformer он отвечает за стабильность входов для следующих Linear, Attention и [[Feed Forward Network|FeedForward]] слоев.

## Причина существования

После Residual Connection значения embedding могут постепенно менять масштаб. Следующие Linear и FeedForward слои должны получать входные данные похожего масштаба.

Без LayerNorm глубокий Transformer труднее стабильно обучать: представления между блоками могут становиться слишком разными по масштабу.

## Простое объяснение

LayerNorm практически повторяет идею [[Statistics/Z-score|z-score]] для одного embedding.

Разница в том, что после стандартизации используются обучаемые параметры `γ` и `β`, позволяющие модели самостоятельно подобрать удобный масштаб и смещение.

## Как это работает

Последовательность вычислений:

1. Получить embedding после Residual.
2. Вычислить среднее значение признаков этого embedding.
3. Вычислить дисперсию и стандартное отклонение.
4. Выполнить стандартизацию признаков.
5. Применить `γ` и `β`.

Результат становится входом следующего слоя Transformer.

В рассмотренной архитектуре LayerNorm применяется после объединения исходного embedding и результата вычислений Attention или FeedForward:

```text
x + F(x)
    ↓
LayerNorm
```

Сначала формируется итоговое представление, и только затем выполняется нормализация. Если нормализовать только результат Attention, а потом прибавить исходный embedding, итоговый embedding снова может получить произвольный масштаб.

## Пример

```python
x = x + attention(x)
x = layer_norm(x)
x = feed_forward(x)
```

В форме Post-Residual Normalization:

```python
x = layer_norm(x + attention(x))
```

## Типичные ошибки

- Считать LayerNorm обычным делением на фиксированное число.
- Считать, что LayerNorm уменьшает числа ради уменьшения.
- Не понимать связь LayerNorm и z-score.
- Считать `γ` и `β` фиксированными константами.
- Нормализовать только результат Attention и забывать про сумму `x + Attention(x)`.

## Связанные темы

[[Transformer Block]] · [[Residual Connection]] · [[Feed Forward Network]] · [[Statistics/Z-score|Z-score]] · [[Statistics/Mean|Mean]] · [[Statistics/Variance|Variance]] · [[Statistics/Standard Deviation|Standard Deviation]]

## Вопросы для проверки

- Почему LayerNorm использует собственные mean и std для каждого embedding?
- Почему `γ` и `β` являются обучаемыми параметрами?
- Почему LayerNorm выполняется после Residual?
- Что произошло бы, если нормализовать только `Attention(x)`, а потом прибавить старый embedding?

## Следующие темы

- Pre-LayerNorm
- Post-LayerNorm
- GPT Architecture
- [[MultiheadAttention в PyTorch]]
