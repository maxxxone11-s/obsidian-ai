---
type: module_plan
area: LLM Engineering
created: 2026-07-07
updated: 2026-07-07
tags:
  - llm-engineering
  - module-plan
---

# LLM Engineering Plan

## Module Goal

Научиться строить production-подобные приложения поверх LLM API: вызывать модели из кода, проектировать prompts, получать structured output, подключать tools, streaming, context management, cost optimization и production-наблюдаемость.

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

## Topics

### 1. Основы LLM API

status: not_started

Коротко: понять, как современные модели вызываются из кода и как устроен базовый request/response цикл.

Related concepts:

- [[Transformers/Index|Transformers]]
- [[Python Backend/FastAPI|FastAPI]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]

Topics:

- Что такое LLM API
- Chat Completions
- Messages
- Roles
- Parameters: temperature, top_p, max_tokens, stop, seed
- Response structure
- Token usage
- Model selection

### 2. Prompt Engineering

status: not_started

Коротко: научиться проектировать prompts так, чтобы модель стабильно понимала задачу, формат ответа и ограничения.

Related concepts:

- [[Transformers/Language Modeling Head|Language Modeling Head]]
- [[Transformers/Temperature Sampling|Temperature Sampling]]
- [[AI Agents/Index|AI Agents]]

Topics:

- Как модель читает промпт
- System Prompt
- User Prompt
- Assistant Messages
- Few-shot
- Chain of Thought
- Prompt Templates
- Delimiters
- Output formatting
- Prompt Injection
- Prompt Versioning

### 3. Structured Output

status: not_started

Коротко: научиться получать от модели валидные структуры данных вместо свободного текста.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]

Topics:

- Почему JSON ломается
- JSON Mode
- Structured Output
- JSON Schema
- Pydantic
- Parsing
- Validation
- Error recovery

### 4. Function Calling

status: not_started

Коротко: понять, как модель выбирает tools/functions и как приложение выполняет tool loop.

Related concepts:

- [[LangGraph/LLM Tool Calling|LLM Tool Calling]]
- [[LangGraph/Tool|Tool]]
- [[LangGraph/Tool Node|Tool Node]]
- [[AI Agents/Index|AI Agents]]

Topics:

- Зачем функции нужны модели
- Tool schema
- Аргументы
- Multiple tools
- Tool loop
- Tool errors
- Tool results
- Tool retry

### 5. Streaming

status: not_started

Коротко: научиться отдавать ответ модели постепенно для лучшего UX.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]

Topics:

- Почему streaming лучше UX
- Token streaming
- SSE
- Async streaming
- Streaming + FastAPI
- Streaming + UI

### 6. Context Engineering

status: not_started

Коротко: научиться управлять context window, историей сообщений и token budget.

Related concepts:

- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Transformers/KV Cache|KV Cache]]
- [[RAG/Index|RAG]]
- [[AI Agents/Index|AI Agents]]

Topics:

- Context Window
- Token budget
- Message history
- Sliding window
- Truncation
- Context compression
- Context prioritization
- Conversation memory

### 7. Cost Optimization

status: not_started

Коротко: научиться снижать стоимость и latency LLM-приложений без потери качества.

Related concepts:

- [[Transformers/Attention Complexity During Inference|Attention Complexity During Inference]]
- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Python Backend/Redis|Redis]]

Topics:

- Token counting
- Prompt optimization
- Caching
- Batch requests
- Model routing
- Cheap vs expensive models
- Latency optimization

### 8. Production Patterns

status: not_started

Коротко: научиться проектировать надёжные LLM-сервисы с retry, timeout, monitoring и fallback.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[Python Backend/Redis|Redis]]
- [[Python Backend/Docker|Docker]]

Topics:

- Retry
- Timeout
- Rate limits
- Exponential backoff
- Logging
- Monitoring
- Fallback models
- Circuit breaker
- Request IDs
- Observability

### 9. Работа с несколькими провайдерами

status: not_started

Коротко: научиться переключать модели и провайдеров без переписывания приложения.

Related concepts:

- [[LLM Engineering/Plan|LLM Engineering Plan]]
- [[Python Backend/FastAPI|FastAPI]]

Topics:

- OpenAI
- Anthropic
- Gemini
- OpenRouter
- Совместимость API
- Переключение моделей

### 10. Финальный проект

status: not_started

Коротко: собрать production-подобный сервис, объединяющий ключевые практики LLM Engineering.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[RAG/Index|RAG]]
- [[AI Agents/Index|AI Agents]]
- [[LangGraph/Index|LangGraph]]

## Practical Projects

- Минимальный FastAPI-сервис для вызова LLM API.
- Endpoint со structured output и валидацией через schema/Pydantic.
- Tool/function calling loop с обработкой ошибок и retry.
- Streaming endpoint для постепенной отдачи ответа.
- Production-подобный финальный сервис:
  - FastAPI
  - LLM API
  - Structured Output
  - Function Calling
  - Streaming
  - Логирование
  - Обработка ошибок
  - Оптимизация стоимости
  - Возможность менять модель без переписывания приложения

## Dependencies

- [[Python Backend/Index|Python Backend]] — FastAPI, async, API design, logging, error handling.
- [[Machine Learning/Index|Machine Learning]] — базовое понимание моделей, параметров и evaluation.
- [[Neural Networks/Index|Neural Networks]] — logits, softmax, inference, training intuition.
- [[PyTorch/Index|PyTorch]] — inference pipeline и чтение ML-кода.
- [[Transformers/Index|Transformers]] — tokens, context, attention, generation, KV Cache.
- [[RAG/Index|RAG]] — внешний контекст, retrieval и vector search.
- [[AI Agents/Index|AI Agents]] — tools, memory, orchestration, agent workflows.

## Future KNOWLEDGE_EXPORT targets

- Что такое LLM API
- Chat Completions
- Messages и Roles
- LLM API Parameters
- Response Structure
- Token Usage
- Model Selection
- System Prompt
- User Prompt
- Few-shot Prompting
- Chain of Thought
- Prompt Templates
- Delimiters
- Output Formatting
- Prompt Injection
- Prompt Versioning
- JSON Mode
- Structured Output
- JSON Schema
- Pydantic Validation
- Parsing and Error Recovery
- Function Calling
- Tool Schema
- Tool Loop
- Tool Errors and Retry
- Token Streaming
- SSE
- Async Streaming
- Streaming with FastAPI
- Context Window
- Token Budget
- Message History
- Sliding Window
- Truncation
- Context Compression
- Context Prioritization
- Conversation Memory
- Token Counting
- Prompt Optimization
- LLM Caching
- Batch Requests
- Model Routing
- Latency Optimization
- Retry and Timeout
- Rate Limits
- Exponential Backoff
- Logging and Monitoring
- Fallback Models
- Circuit Breaker
- Request IDs
- Observability
- Multi-provider LLM Architecture
- OpenAI Provider
- Anthropic Provider
- Gemini Provider
- OpenRouter Provider
- Final LLM Engineering Service
