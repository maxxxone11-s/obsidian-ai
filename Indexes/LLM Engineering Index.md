---
type: index
area: LLM Engineering
created: 2026-06-26
updated: 2026-07-10
tags:
  - index
  - system
  - llm-engineering
---

# LLM Engineering Index

Указатель области LLM Engineering.

## Module Plan

- [[LLM Engineering/Plan|LLM Engineering Plan]]

## Learning Path

1. Основы LLM API
2. Prompt Engineering
3. Structured Output
4. Function Calling
5. Streaming
6. Context Engineering
7. Cost Optimization
8. Production Patterns
9. Работа с несколькими провайдерами
10. Финальный production-подобный сервис

## Future Concept Notes

### Основы LLM API

- [[LLM Engineering/OpenRouter через OpenAI SDK|OpenRouter через OpenAI SDK]]
- [[LLM Engineering/Архитектура OpenAI SDK|Архитектура OpenAI SDK]]
- [[LLM Engineering/Цепочка выполнения chat.completions.create|Цепочка выполнения chat.completions.create]]
- [[LLM Engineering/Messages как источник контекста модели|Messages как источник контекста модели]]
- [[LLM Engineering/Top-p (Nucleus Sampling)|Top-p (Nucleus Sampling)]]
- [[LLM Engineering/Max Tokens|Max Tokens]]
- [[LLM Engineering/Stop Sequence|Stop Sequence]]
- Что такое LLM API
- Chat Completions
- Messages и Roles
- LLM API Parameters
- Response Structure
- Token Usage
- Model Selection

### Prompt Engineering

- [[LLM Engineering/Prompt Engineering|Prompt Engineering]]
- [[LLM Engineering/System Prompt|System Prompt]]
- [[LLM Engineering/User Prompt|User Prompt]]
- [[LLM Engineering/Few-shot Prompting|Few-shot Prompting]]
- Chain of Thought
- [[LLM Engineering/Prompt Templates|Prompt Templates]]
- [[LLM Engineering/Delimiters|Delimiters]]
- [[LLM Engineering/Output Formatting|Output Formatting]]
- Prompt Injection
- Prompt Versioning

### Structured Output

- JSON Mode
- [[LLM Engineering/Structured Output|Structured Output]]
- [[LLM Engineering/JSON Schema|JSON Schema]]
- [[LLM Engineering/Pydantic в Structured Output|Pydantic в Structured Output]]
- [[LLM Engineering/Validation|Validation]]
- [[LLM Engineering/Error Recovery|Error Recovery]]
- Parsing

### Function Calling

- Function Calling
- Tool Schema
- Tool Loop
- Tool Errors and Retry

### Streaming

- Token Streaming
- SSE
- Async Streaming
- Streaming with FastAPI

### Context Engineering

- Context Window
- Token Budget
- Message History
- Sliding Window
- Truncation
- Context Compression
- Context Prioritization
- Conversation Memory

### Cost Optimization

- Token Counting
- Prompt Optimization
- LLM Caching
- Batch Requests
- Model Routing
- Latency Optimization

### Production Patterns

- Retry and Timeout
- Rate Limits
- Exponential Backoff
- Logging and Monitoring
- Fallback Models
- Circuit Breaker
- Request IDs
- Observability

### Providers

- Multi-provider LLM Architecture
- OpenAI Provider
- Anthropic Provider
- Gemini Provider
- OpenRouter Provider

### Final Project

- Final LLM Engineering Service
