---
type: module_plan
area: LLM Engineering
created: 2026-07-07
updated: 2026-07-10
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

status: learned

Коротко: понять, как современные модели вызываются из кода и как устроен базовый request/response цикл.

Related concepts:

- [[Transformers/Transformers|Transformers]]
- [[Python Backend/FastAPI|FastAPI]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]
- [[OpenRouter через OpenAI SDK]]
- [[Архитектура OpenAI SDK]]
- [[Цепочка выполнения chat.completions.create]]
- [[Messages как источник контекста модели]]
- [[Transformers/Temperature Sampling|Temperature Sampling]]
- [[Top-p (Nucleus Sampling)]]
- [[Max Tokens]]
- [[Stop Sequence]]

Topics:

- Что такое LLM API
- OpenRouter через OpenAI SDK — learned
- Архитектура OpenAI SDK — learned
- Цепочка выполнения `chat.completions.create` — learned
- Messages — learned
- Roles
- Parameters: temperature — learned
- Parameters: top_p — learned
- Parameters: max_tokens — learned
- Parameters: stop — learned
- Parameters: seed — not_started
- Response structure
- Token usage
- Model selection

### 2. Prompt Engineering

status: learned

Коротко: научиться проектировать prompts так, чтобы модель стабильно понимала задачу, формат ответа и ограничения.

Related concepts:

- [[Transformers/Language Modeling Head|Language Modeling Head]]
- [[Transformers/Temperature Sampling|Temperature Sampling]]
- [[AI Agents/AI Agents|AI Agents]]
- [[Prompt Engineering]]
- [[System Prompt]]
- [[User Prompt]]
- [[Prompt Templates]]
- [[Few-shot Prompting]]
- [[Delimiters]]
- [[Output Formatting]]

Topics:

- Как модель читает промпт
- System Prompt — learned
- User Prompt — learned
- Assistant Messages
- Few-shot — learned
- Chain of Thought
- Prompt Templates — learned
- Delimiters — learned
- Output formatting — learned
- Prompt Injection
- Prompt Versioning

### 3. Structured Output

status: learned

Коротко: научиться получать от модели валидные структуры данных вместо свободного текста.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]
- [[Structured Output]]
- [[JSON Schema]]
- [[Pydantic в Structured Output]]
- [[LLM Engineering/Response Validation]]
- [[Error Recovery]]

Topics:

- Почему JSON ломается
- JSON Mode
- Structured Output — learned
- JSON Schema — learned
- Pydantic — learned
- Parsing
- Validation — learned
- Error recovery — learned

### 4. Function Calling

status: learned

Коротко: понять, как модель выбирает tools/functions и как приложение выполняет tool loop.

Related concepts:

- [[LangGraph/LLM Tool Calling|LLM Tool Calling]]
- [[LangGraph/Tool|Tool]]
- [[LangGraph/Tool Node|Tool Node]]
- [[AI Agents/AI Agents|AI Agents]]
- [[Function Calling]]
- [[Function Schema]]
- [[Tool Selection]]
- [[Tool Loop]]
- [[Multiple Tool Calls]]
- [[Tool Calling]]

Topics:

- Зачем функции нужны модели — learned
- Tool schema — learned
- Аргументы — learned
- Multiple tools — learned
- Tool selection — learned
- Tool loop — learned
- Tool errors
- Tool results — learned
- Tool retry

### 5. Streaming

status: learned

Коротко: научиться отдавать ответ модели постепенно для лучшего UX.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[PyTorch/Inference Pipeline|Inference Pipeline]]
- [[Streaming]]
- [[Streaming API в OpenAI SDK]]
- [[Streaming при Function Calling]]

Topics:

- Почему streaming лучше UX — learned
- Token streaming — learned
- Streaming API в OpenAI SDK — learned
- Streaming при Function Calling — learned
- SSE
- Async streaming
- Streaming + FastAPI
- Streaming + UI

### 6. Context Engineering

status: learned

Коротко: научиться управлять context window, историей сообщений и token budget.

Related concepts:

- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Transformers/KV Cache|KV Cache]]
- [[RAG/RAG|RAG]]
- [[AI Agents/AI Agents|AI Agents]]
- [[Context Window]]
- [[Переполнение Context Window]]
- [[Token Counting]]
- [[Conversation Memory]]
- [[Conversation State]]
- [[Memory Management]]

Topics:

- Context Window — learned
- Context overflow — learned
- Token counting — learned
- Token budget — learned
- Message history — learned
- Sliding window
- Truncation
- Context compression
- Context prioritization
- Conversation memory — learned
- Conversation state — learned
- Memory management — learned

### 7. Cost Optimization

status: learned

Коротко: научиться снижать стоимость и latency LLM-приложений без потери качества.

Related concepts:

- [[Transformers/Attention Complexity During Inference|Attention Complexity During Inference]]
- [[Transformers/Context Window vs KV Cache|Context Window vs KV Cache]]
- [[Python Backend/Redis|Redis]]
- [[Стоимость LLM-запросов]]
- [[Cost Optimization]]
- [[Исключение ненужных вызовов LLM]]
- [[Model Routing]]
- [[Prompt Caching]]
- [[Production Pipeline LLM-приложения]]

Topics:

- Token counting — learned
- Prompt optimization
- Cost structure — learned
- Avoid unnecessary LLM calls — learned
- Prompt caching — learned
- Batch requests
- Model routing — learned
- Cheap vs expensive models
- Latency optimization

### 8. Production Patterns

status: not_started

Коротко: научиться проектировать надёжные LLM-сервисы с retry, timeout, monitoring и fallback.

Related concepts:

- [[Python Backend/FastAPI|FastAPI]]
- [[Python Backend/Redis|Redis]]
- [[Python Backend/Docker|Docker]]
- [[Production Pipeline LLM-приложения]]

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
- [[RAG/RAG|RAG]]
- [[AI Agents/AI Agents|AI Agents]]
- [[LangGraph/LangGraph|LangGraph]]

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

- [[Python Backend/Python Backend|Python Backend]] — FastAPI, async, API design, logging, error handling.
- [[Machine Learning/Machine Learning|Machine Learning]] — базовое понимание моделей, параметров и evaluation.
- [[Neural Networks/Neural Networks|Neural Networks]] — logits, softmax, inference, training intuition.
- [[PyTorch/PyTorch|PyTorch]] — inference pipeline и чтение ML-кода.
- [[Transformers/Transformers|Transformers]] — tokens, context, attention, generation, KV Cache.
- [[RAG/RAG|RAG]] — внешний контекст, retrieval и vector search.
- [[AI Agents/AI Agents|AI Agents]] — tools, memory, orchestration, agent workflows.

## Future KNOWLEDGE_EXPORT targets

- Что такое LLM API
- Chat Completions
- Messages и Roles
- LLM API Parameters
- Response Structure
- Token Usage
- Model Selection
- Max Tokens
- Stop Sequence
- OpenRouter через OpenAI SDK
- Архитектура OpenAI SDK
- Цепочка выполнения chat.completions.create
- Messages как источник контекста модели
- Top-p (Nucleus Sampling)
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
- Validation
- Error Recovery
- Parsing
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
