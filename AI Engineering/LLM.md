---
type: concept
area: llm-engineering
status: draft
created: 2026-06-26
updated: 2026-06-27
tags: [llm, language-model, transformer]
confidence: 0
---

# LLM

Large Language Model — большая языковая модель.

## Простое объяснение

LLM — это нейронная сеть, которая предсказывает следующее слово на основе предыдущих.

## Интуитивное объяснение

Как предиктивный текст на телефоне, но намного мощнее.

## Зачем это нужно

- Генерация текста
- Понимание текста
- Основа для AI систем

## Как это работает

### Архитектура
- Transformer
- Attention mechanism
- Token-based processing

## Пример

```python
from openai import OpenAI

client = OpenAI()
response = client.chat.completions.create(
    model="gpt-4",
    messages=[{"role": "user", "content": "Hello"}]
)
```

## Типичные ошибки

- Неправильный prompt
- Температура слишком высокая/низкая
- Забывают про токены лимит

## Связанные темы

- [[RAG]] — добавляет контекст к LLM
- [[Embeddings]] — компонент многих LLM
- [[AI Agent]] — использует LLM для решения задач
- [[Vector Database]] — часто используется с LLM
