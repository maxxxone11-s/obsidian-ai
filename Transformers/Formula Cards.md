---
type: index
area: Transformers
knowledge_area: Transformers
created: 2026-07-04
updated: 2026-07-04
tags:
  - transformers
  - formulas
---

# Transformers Formula Cards

## Token + Position Embedding

**Formula**

$$
x = tok\_emb + pos\_emb
$$

**Symbols**

- `x` — входной embedding для Transformer Block
- `tok_emb` — token embedding
- `pos_emb` — position embedding

**Function**

Объединяет смысл токена и информацию о его позиции.

**Simple explanation**

Модель складывает два embedding одинаковой размерности, чтобы не увеличивать размер входа для следующих слоёв.

**Related concepts**

- [[Embedding Layer]]
- [[Position Embedding]]
- [[Transformer Block]]

## Query, Key, Value Projections

**Formula**

$$
Q = XW_q
$$

$$
K = XW_k
$$

$$
V = XW_v
$$

**Symbols**

- `X` — входные embedding
- `W_q` — матрица весов для Query
- `W_k` — матрица весов для Key
- `W_v` — матрица весов для Value
- `Q` — Query
- `K` — Key
- `V` — Value

**Function**

Создаёт три разных представления одного embedding для attention.

**Simple explanation**

Один и тот же embedding преобразуется в три роли: что искать, по чему искать и какую информацию передавать.

**Related concepts**

- [[Query Key Value]]
- [[Self-Attention Pipeline]]
- [[Multi-Head Attention]]
- [[PyTorch/nn.Linear|nn.Linear]]

## Combined QKV Projection

**Formula**

$$
Linear(d_{model} \rightarrow 3d_{model})
$$

**Symbols**

- `d_model` — размерность embedding модели
- `3d_model` — объединённая размерность для Q, K и V

**Function**

Вычисляет Query, Key и Value одним большим Linear-слоем.

**Simple explanation**

Вместо трёх отдельных Linear модель делает одну большую проекцию, а потом разделяет результат на Q, K и V.

**Related concepts**

- [[Query Key Value]]
- [[MultiheadAttention в PyTorch]]
- [[Self-Attention Pipeline]]

## Attention Scores

**Formula**

$$
Scores = \frac{QK^T}{\sqrt{head\_dim}}
$$

**Symbols**

- `Q` — Query
- `K^T` — транспонированный Key
- `head_dim` — размерность одной attention head
- `Scores` — матрица attention scores

**Function**

Вычисляет похожесть между Query и Key с масштабированием.

**Simple explanation**

Модель сравнивает каждый токен с каждым другим токеном, а деление на корень из `head_dim` удерживает значения в удобном диапазоне для Softmax.

**Related concepts**

- [[Attention Scores]]
- [[Query Key Value]]
- [[Neural Networks/Softmax|Softmax]]
- [[Statistics/Standard Deviation|Standard Deviation]]

## Attention Weights

**Formula**

$$
Attention = softmax(Scores)
$$

**Symbols**

- `Scores` — сырые attention scores
- `softmax` — нормализация в распределение весов
- `Attention` — attention weights

**Function**

Преобразует scores в веса внимания.

**Simple explanation**

Scores ещё не говорят, какую долю информации брать. Softmax превращает их в нормализованные веса.

**Related concepts**

- [[Attention Weights]]
- [[Attention Scores]]
- [[Neural Networks/Softmax|Softmax]]

## Attention Output

**Formula**

$$
output = weights \cdot V
$$

**Symbols**

- `weights` — attention weights
- `V` — Value
- `output` — новый контекстный embedding

**Function**

Собирает новый embedding как взвешенную сумму Value.

**Simple explanation**

После выбора важных токенов модель берёт от них информацию в нужных пропорциях.

**Related concepts**

- [[Attention Output]]
- [[Attention Weights]]
- [[Query Key Value]]

## Full Self-Attention Pipeline

**Formula**

$$
output = softmax(mask(\frac{QK^T}{\sqrt{head\_dim}}))V
$$

**Symbols**

- `Q` — Query
- `K^T` — транспонированный Key
- `head_dim` — размерность attention head
- `mask` — causal mask
- `V` — Value
- `output` — новый embedding

**Function**

Описывает полную цепочку self-attention: scores, scaling, mask, softmax и смешивание Value.

**Simple explanation**

Модель считает похожесть токенов, закрывает запрещённое будущее, превращает scores в веса и собирает новый embedding из Value.

**Related concepts**

- [[Self-Attention Pipeline]]
- [[Causal Mask]]
- [[Attention Scores]]
- [[Attention Weights]]
- [[Attention Output]]

## Single Attention Head

**Formula**

$$
Head_i = Attention(XW_{q_i}, XW_{k_i}, XW_{v_i})
$$

**Symbols**

- `Head_i` — i-я attention head
- `X` — входные embedding
- `W_{q_i}` — Query-веса i-й головы
- `W_{k_i}` — Key-веса i-й головы
- `W_{v_i}` — Value-веса i-й головы

**Function**

Описывает вычисление одной attention head внутри Multi-Head Attention.

**Simple explanation**

Каждая голова получает тот же вход, но использует свои веса и строит своё представление связей между токенами.

**Related concepts**

- [[Multi-Head Attention]]
- [[Query Key Value]]
- [[Attention Scores]]

## Multi-Head Output Projection

**Formula**

$$
Concat(Head_1, Head_2, ..., Head_N) \rightarrow Linear(d_{model} \rightarrow d_{model})
$$

**Symbols**

- `Head_1 ... Head_N` — результаты attention heads
- `Concat` — объединение результатов голов
- `d_model` — размерность embedding модели

**Function**

Объединяет результаты нескольких heads и возвращает embedding в размерность модели.

**Simple explanation**

После работы голов их результаты лежат рядом. Output Projection смешивает их обратно в один общий embedding.

**Related concepts**

- [[Multi-Head Attention]]
- [[Attention Output]]
- [[PyTorch/nn.Linear|nn.Linear]]

## LayerNorm

**Formula**

$$
LayerNorm(x) = \gamma \cdot \frac{x - \mu}{\sqrt{\sigma^2 + \varepsilon}} + \beta
$$

**Symbols**

- `x` — входной embedding
- `μ` — среднее значение признаков текущего embedding
- `σ²` — дисперсия признаков текущего embedding
- `ε` — малая константа против деления на ноль
- `γ` — обучаемый коэффициент масштабирования
- `β` — обучаемое смещение

**Function**

Нормализует признаки embedding и затем даёт модели обучаемо настроить масштаб и смещение.

**Simple explanation**

LayerNorm делает embedding статистически стабильнее, но не лишает модель возможности подобрать удобный масштаб.

**Related concepts**

- [[LayerNorm]]
- [[Pre-LayerNorm]]
- [[Residual Connection]]
- [[Statistics/Z-score|Z-score]]

## Post-LayerNorm

**Formula**

$$
x = ln(x + attn(x))
$$

**Symbols**

- `x` — текущий embedding
- `attn(x)` — результат attention
- `ln` — LayerNorm

**Function**

Сначала добавляет residual, затем нормализует результат.

**Simple explanation**

Модель сначала объединяет старое представление и результат attention, а потом стабилизирует итоговый embedding.

**Related concepts**

- [[LayerNorm]]
- [[Residual Connection]]
- [[Pre-LayerNorm]]

## Pre-LayerNorm

**Formula**

$$
x = x + attn(ln(x))
$$

**Symbols**

- `x` — текущий embedding
- `ln(x)` — нормализованный вход
- `attn` — attention module

**Function**

Нормализует вход до attention, а результат добавляет через residual.

**Simple explanation**

Сначала модель стабилизирует вход модуля, потом считает attention и прибавляет результат к исходному embedding.

**Related concepts**

- [[Pre-LayerNorm]]
- [[LayerNorm]]
- [[Residual Connection]]
- [[nanoGPT Architecture]]

## LM Head Projection

**Formula**

$$
Linear(d_{model} \rightarrow vocab\_size)
$$

**Symbols**

- `d_model` — размерность final embedding
- `vocab_size` — размер словаря токенов

**Function**

Преобразует final embedding в logits по всему словарю.

**Simple explanation**

Модель переводит внутреннее представление в оценки для каждого возможного следующего токена.

**Related concepts**

- [[Language Modeling Head]]
- [[Neural Networks/Logits|Logits]]
- [[Temperature Sampling]]

## Weight Tying Output

**Formula**

$$
logits = final\_embedding \cdot embedding\_matrix^T
$$

**Symbols**

- `final_embedding` — финальное представление токена
- `embedding_matrix^T` — транспонированная token embedding matrix
- `logits` — оценки токенов словаря

**Function**

Использует token embedding matrix как выходную матрицу для LM Head.

**Simple explanation**

Одна и та же таблица помогает и получать embedding на входе, и сравнивать финальное представление со всеми токенами на выходе.

**Related concepts**

- [[Weight Tying]]
- [[Embedding Layer]]
- [[Language Modeling Head]]
- [[Neural Networks/Logits|Logits]]

## Temperature Sampling

**Formula**

$$
Softmax(\frac{Logits}{T})
$$

**Symbols**

- `Logits` — сырые оценки токенов
- `T` — temperature
- `Softmax` — преобразование logits в распределение вероятностей

**Function**

Управляет резкостью распределения вероятностей при генерации.

**Simple explanation**

Меньшая temperature делает выбор более уверенным, большая — более разнообразным.

**Related concepts**

- [[Temperature Sampling]]
- [[Language Modeling Head]]
- [[Neural Networks/Softmax|Softmax]]
- [[Autoregressive Generation]]

## FeedForward Expansion

**Formula**

$$
n_{embd} \rightarrow 4 \times n_{embd} \rightarrow GELU \rightarrow n_{embd}
$$

**Symbols**

- `n_embd` — размерность embedding модели
- `4 × n_embd` — расширенная внутренняя размерность FeedForward
- `GELU` — нелинейная функция активации

**Function**

Временно расширяет пространство признаков внутри FeedForward, применяет нелинейность и возвращает embedding к исходной размерности.

**Simple explanation**

MLP сначала даёт модели больше внутреннего пространства для построения признаков, затем сжимает результат обратно до размера, совместимого с Transformer Block.

**Related concepts**

- [[Feed Forward Network]]
- [[Transformer Block]]
- [[PyTorch/nn.Linear|nn.Linear]]
