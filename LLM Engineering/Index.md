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

# LLM Engineering

Инженерные подходы к построению приложений поверх Large Language Models.

## План модуля

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

## Основные блоки

### LLM API

- [[OpenRouter через OpenAI SDK]]
- [[Архитектура OpenAI SDK]]
- [[Цепочка выполнения chat.completions.create]]
- [[Messages как источник контекста модели]]
- [[Top-p (Nucleus Sampling)]]
- [[Max Tokens]]
- [[Stop Sequence]]
- Chat Completions
- Messages и Roles
- Parameters
- Response structure
- Token usage
- Model selection

### Prompt Engineering

- [[Prompt Engineering]]
- [[System Prompt]]
- [[User Prompt]]
- [[Few-shot Prompting]]
- Chain of Thought
- [[Prompt Templates]]
- [[Delimiters]]
- [[Output Formatting]]
- Prompt Injection
- Prompt Versioning

### Structured Output

- JSON Mode
- [[Structured Output]]
- [[JSON Schema]]
- [[Pydantic в Structured Output]]
- Parsing
- [[Validation]]
- [[Error Recovery]]

### Function Calling

- [[Function Calling]]
- [[Function Schema]]
- [[Tool Selection]]
- [[Tool Loop]]
- [[Multiple Tool Calls]]
- [[Tool Calling]]
- Tool errors
- Tool retry

### Streaming

- [[Streaming]]
- [[Streaming API в OpenAI SDK]]
- [[Streaming при Function Calling]]
- SSE
- Async streaming
- Streaming + FastAPI

### Context Engineering

- [[Context Window]]
- [[Переполнение Context Window]]
- [[Token Counting]]
- [[Conversation Memory]]
- [[Conversation State]]
- [[Memory Management]]
- Token budget
- Message history
- Sliding window
- Context compression

### Production Engineering

- Cost optimization
- Retry
- Timeout
- Rate limits
- Logging
- Monitoring
- Fallback models
- Observability

## Практика

- FastAPI service для LLM API.
- Structured output endpoint.
- Function calling loop.
- Streaming endpoint.
- Production-подобный финальный сервис.

## Связанные области

- [[Python Backend/Index|Python Backend]]
- [[Transformers/Index|Transformers]]
- [[Transformers/Temperature Sampling|Temperature Sampling]]
- [[RAG/Index|RAG]]
- [[AI Agents/Index|AI Agents]]
- [[LangGraph/Index|LangGraph]]
