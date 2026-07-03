---
type: index
area: Transformers
knowledge_area: Transformers
created: 2026-06-30
updated: 2026-07-03
tags:
  - index
  - system
  - transformers
---

# Transformers Index

Указатель области Transformers организован по знаниям, а не по урокам. История курса сохранена отдельно в разделе Course Progress.

## Core Concepts

- [[Transformers/Embedding Layer|Embedding Layer]]
- [[Transformers/Position Embedding|Position Embedding]]
- [[Transformers/Статический и контекстный Embedding|Статический и контекстный Embedding]]
- [[Transformers/Embedding Space|Embedding Space]]
- [[Transformers/Query Key Value|Query Key Value]]
- [[Transformers/Self-Attention Pipeline|Self-Attention Pipeline]]
- [[Transformers/Attention Scores|Attention Scores]]
- [[Transformers/Attention Weights|Attention Weights]]
- [[Transformers/Attention Output|Attention Output]]
- [[Transformers/Multi-Head Attention|Multi-Head Attention]]

## Transformer Architecture

- [[Transformers/Transformer Block|Transformer Block]]
- [[Transformers/Transformer Block Interface|Transformer Block Interface]]
- [[Transformers/Residual Connection|Residual Connection]]
- [[Transformers/LayerNorm|LayerNorm]]
- [[Transformers/Pre-LayerNorm|Pre-LayerNorm]]
- [[Transformers/Feed Forward Network|Feed Forward Network]]
- [[Transformers/Постепенное уточнение embedding|Постепенное уточнение embedding]]

## Generation & Inference

- [[Transformers/KV Cache|KV Cache]]
- [[Transformers/Attention Complexity During Inference|Attention Complexity During Inference]]
- [[Transformers/Language Modeling Head|Language Modeling Head]]
- [[Transformers/Temperature Sampling|Temperature Sampling]]
- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Transformers/nanoGPT Architecture|nanoGPT Architecture]]

## PyTorch Implementation

- [[Transformers/MultiheadAttention в PyTorch|MultiheadAttention в PyTorch]]
- [[Transformers/Module и Functional в PyTorch|Module и Functional в PyTorch]]
- [[Transformers/nn.Module __call__|nn.Module __call__]]
- [[Transformers/Batch Matrix Multiplication|Batch Matrix Multiplication]]

## Related Knowledge

### PyTorch

- [[PyTorch/nn.Linear|nn.Linear]]
- [[PyTorch/Matrix Multiplication in PyTorch (matmul)|Matrix Multiplication in PyTorch]]

### Neural Networks

- [[Neural Networks/Softmax|Softmax]]

### Statistics

- [[Statistics/Z-score|Z-score]]

## Course Progress

### Transformer Foundations I

New Concepts:
- Embedding Layer
- Статический и контекстный Embedding
- Query Key Value
- Attention Scores
- Attention Weights
- Attention Output
- Embedding Space
- MultiheadAttention в PyTorch

Updated Concepts:
- none

Learning Goal:
Понять путь от token id к contextual embedding: как embedding table, QKV, attention scores, softmax weights и weighted sum превращают исходный токен в контекстное представление. Увидеть связь между математикой Self-Attention и инженерной реализацией PyTorch.

### Transformer Foundations II

New Concepts:
- Transformer Block
- Residual Connection
- Постепенное уточнение embedding
- Feed Forward Network
- Module и Functional в PyTorch
- Batch Matrix Multiplication
- LayerNorm

Updated Concepts:
- MultiheadAttention в PyTorch

Learning Goal:
Понять Transformer Block как инженерную единицу архитектуры: Attention собирает контекст, Residual сохраняет исходное представление, LayerNorm стабилизирует масштаб, а FeedForward строит новые признаки. Разобрать, почему PyTorch реализует эти операции через эффективные tensor operations.

### Transformer Foundations III

New Concepts:
- none

Updated Concepts:
- LayerNorm
- Residual Connection
- Feed Forward Network

Learning Goal:
Уточнить инженерный смысл LayerNorm, порядок Residual → LayerNorm и роль FeedForward как position-wise MLP. Связать статистическую нормализацию с устойчивостью глубокого Transformer Block.

### Transformer Foundations IV

New Concepts:
- Multi-Head Attention

Updated Concepts:
- Query Key Value
- MultiheadAttention в PyTorch
- Batch Matrix Multiplication

Learning Goal:
Понять Multi-Head Attention как параллельный набор independent attention heads и увидеть, как head projection, output projection, tensor reshaping и объединение batch × heads превращают идею в эффективную PyTorch-реализацию.

### Transformers Generation Module

New Concepts:
- KV Cache
- Attention Complexity During Inference
- Language Modeling Head
- Temperature Sampling
- Context Window vs KV Cache
- nanoGPT Architecture

Updated Concepts:
- Постепенное уточнение embedding

Learning Goal:
Понять инженерный путь генерации текста: как Transformer превращает final embedding в logits, как sampling управляет выбором токена, почему KV Cache ускоряет autoregressive generation и где проходят границы между context window, cache и памятью приложения.

### Transformer Architecture Module

New Concepts:
- Position Embedding
- Pre-LayerNorm
- Transformer Block Interface
- nn.Module __call__
- Self-Attention Pipeline

Updated Concepts:
- Embedding Layer
- Residual Connection
- LayerNorm
- Query Key Value
- Multi-Head Attention

Learning Goal:
Понять GPT как модульную инженерную архитектуру: как token и position embeddings формируют вход, как Block скрывает внутреннюю реализацию за стабильным интерфейсом, как Pre-LN меняет порядок вычислений и как QKV, Scores, Weights и Value складываются в полный Self-Attention pipeline.
