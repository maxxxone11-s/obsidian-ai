---
type: index
area: Transformers
knowledge_area: Transformers
created: 2026-06-30
updated: 2026-07-06
tags:
  - index
  - system
  - transformers
---

# Transformers

Индекс области Transformers организован по знаниям, а не по урокам. История курса сохранена отдельно в разделе Course Progress.

## Core Concepts

- [[Embedding Layer]]
- [[Position Embedding]]
- [[GPTConfig]]
- [[Статический и контекстный Embedding]]
- [[Embedding Space]]
- [[Query Key Value]]
- [[Self-Attention Pipeline]]
- [[Attention Scores]]
- [[Causal Mask]]
- [[Attention Weights]]
- [[Attention Output]]
- [[Multi-Head Attention]]

## Transformer Architecture

- [[Transformer Block]]
- [[Transformer Block Interface]]
- [[ModuleList]]
- [[Residual Connection]]
- [[LayerNorm]]
- [[Pre-LayerNorm]]
- [[Feed Forward Network]]
- [[Постепенное уточнение embedding]]

## Generation & Inference

- [[KV Cache]]
- [[Autoregressive Generation]]
- [[Attention Complexity During Inference]]
- [[Language Modeling Head]]
- [[Weight Tying]]
- [[Temperature Sampling]]
- [[Context Window vs KV Cache]]
- [[Веса как долговременная память модели]]
- [[Разделение ролей LLM и RAG]]
- [[nanoGPT Architecture]]

## PyTorch Implementation

- [[MultiheadAttention в PyTorch]]
- [[Module и Functional в PyTorch]]
- [[nn.Module __call__]]
- [[Batch Matrix Multiplication]]

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

### Transformers Module

New Concepts:
- Causal Mask
- Веса как долговременная память модели
- Разделение ролей LLM и RAG
- Weight Tying
- Autoregressive Generation

Updated Concepts:
- Attention Scores
- Query Key Value
- Language Modeling Head
- Embedding Layer
- KV Cache
- Context Window vs KV Cache
- Постепенное уточнение embedding
- Self-Attention Pipeline

Learning Goal:
Замкнуть архитектурную картину decoder-only Transformer: понять, как causal mask делает параллельное обучение честным, почему attention scores масштабируются, где хранятся знания модели, как LLM отличается от RAG и как autoregressive generation превращает logits в последовательный текст.

### Transformers nanoGPT Source Code

New Concepts:
- GPTConfig
- ModuleList

Updated Concepts:
- Embedding Layer
- Position Embedding
- nanoGPT Architecture
- Transformer Block
- Постепенное уточнение embedding

Learning Goal:
Научиться читать `GPT.__init__` в nanoGPT как инженерную сборку модели: config задаёт размеры, `nn.Embedding` делает lookup в обучаемой таблице, WTE и WPE складываются, ModuleList регистрирует независимые blocks, а Dropout применяется перед первым Transformer Block.
