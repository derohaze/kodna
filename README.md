# Kodna API Documentation

## 🚀 Quick Start

Get started with Kodna API in seconds. Our API is fully compatible with OpenAI's SDK.

---

## 📦 Installation

### Python
```bash
pip install openai
```

### JavaScript / Node.js
```bash
npm install openai
```

---

## 🔑 Usage Examples

### Python
```python
from openai import OpenAI

client = OpenAI(
    base_url="http://api.kodnastudio.com/v1",
    api_key="your-api-key"
)

response = client.chat.completions.create(
    model="claude-opus-4-5-20251101",
    messages=[{"role": "user", "content": "Hello!"}]
)

print(response.choices[0].message.content)
```

### JavaScript / TypeScript
```javascript
import OpenAI from 'openai';

const client = new OpenAI({
    baseURL: 'http://api.kodnastudio.com/v1',
    apiKey: 'your-api-key'
});

const response = await client.chat.completions.create({
    model: 'claude-opus-4-5-20251101',
    messages: [{ role: 'user', content: 'Hello!' }]
});

console.log(response.choices[0].message.content);
```

### cURL
```bash
curl http://api.kodnastudio.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -d '{
    "model": "claude-opus-4-5-20251101",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

---

## 📚 Available Models

### Anthropic / Claude

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `claude-opus-4-5-20251101` | 200K | 64K | Premium |
| `claude-opus-4-1-20250805` | 80K | 32K | Available |
| `claude-sonnet-4-5-20250929` | 200K | 64K | Available |
| `claude-sonnet-4-20250514` | 128K | 64K | Available |
| `claude-haiku-4-5-20251001` | 200K | 32K | Available |

<details>
<summary>📋 Copy Model IDs</summary>

```
claude-opus-4-5-20251101
claude-opus-4-1-20250805
claude-sonnet-4-5-20250929
claude-sonnet-4-20250514
claude-haiku-4-5-20251001
```

</details>

### OpenAI / GPT

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `gpt-5.1` | 128K | 64K | Premium |
| `gpt-5` | 128K | 64K | Premium |
| `gpt-4.1` | 128K | 16K | Available |
| `gpt-4o` | 128K | 4K | Available |
| `gpt-4o-mini` | 128K | 4K | Available |
| `gpt-3.5-turbo` | 16K | 4K | Available |
| `openai-gpt-oss-20b` | 128K | 128K | Available |
| `openai-gpt-oss-120b` | 128K | 128K | Available |

<details>
<summary>📋 Copy Model IDs</summary>

```
gpt-5.1
gpt-5
gpt-4.1
gpt-4o
gpt-4o-mini
gpt-3.5-turbo
openai-gpt-oss-20b
openai-gpt-oss-120b
```

</details>

### Google / Gemini

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `gemini-2.5-pro` | 128K | 64K | Premium |
| `gemini-2.5-flash` | 196K | 32K | Available |
| `gemini-2.0-flash` | 128K | 64K | Available |
| `gemini-1.5-pro` | 128K | 64K | Available |
| `gemini-1.5-flash` | 128K | 64K | Available |
| `gemini-pro` | 128K | 64K | Available |

<details>
<summary>📋 Copy Model IDs</summary>

```
gemini-2.5-pro
gemini-2.5-flash
gemini-2.0-flash
gemini-1.5-pro
gemini-1.5-flash
gemini-pro
```

</details>

### DeepSeek

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `deepseek-v3.2` | 128K | 64K | Available |
| `deepseek-ai/deepseek-v3.1` | 128K | 16K | Available |
| `deepseek-ai/deepseek-v3.1-terminus` | 164K | 56K | Available |
| `deepseek-r1-distill-llama-70b` | 128K | 128K | Available |

<details>
<summary>📋 Copy Model IDs</summary>

```
deepseek-v3.2
deepseek-ai/deepseek-v3.1
deepseek-ai/deepseek-v3.1-terminus
deepseek-r1-distill-llama-70b
```

</details>

### Qwen / Alibaba

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `qwen/qwen3-next-80b-a3b-instruct` | 262K | 16K | Available |

<details>
<summary>📋 Copy Model ID</summary>

```
qwen/qwen3-next-80b-a3b-instruct
```

</details>

### Mistral AI

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `mistralai/mistral-nemotron` | 128K | 16K | Available |

<details>
<summary>📋 Copy Model ID</summary>

```
mistralai/mistral-nemotron
```

</details>

### Meta / Llama

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `llama3.3-70b-instruct` | 131K | 131K | Available |
| `llama3-8b-instruct` | 8K | 8K | Available |

<details>
<summary>📋 Copy Model IDs</summary>

```
llama3.3-70b-instruct
llama3-8b-instruct
```

</details>

### Moonshot AI

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `moonshotai/kimi-k2-instruct-0905` | 256K | 56K | Available |

<details>
<summary>📋 Copy Model ID</summary>

```
moonshotai/kimi-k2-instruct-0905
```

</details>

### Minimax

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `minimaxai/minimax-m2` | 128K | 32K | Available |

<details>
<summary>📋 Copy Model ID</summary>

```
minimaxai/minimax-m2
```

</details>

### Grok / xAI

| Model ID | Context | Output | Status |
|----------|--------|--------|--------|
| `grok-4.1-fast-reasoning` | 200K | 64K | Available |
| `grok-4.1-fast-non-reasoning` | 200K | 64K | Available |

<details>
<summary>📋 Copy Model IDs</summary>

```
grok-4.1-fast-reasoning
grok-4.1-fast-non-reasoning
```

</details>

> **💡 Tip**: Click the "📋 Copy Model IDs" section below each table to expand and copy model IDs easily. GitHub provides a copy button for code blocks.

---

## 🔗 API Reference

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/v1/chat/completions` | POST | Create chat completion |
| `/v1/models` | GET | List available models |

### Base URL
```
http://api.kodnastudio.com/v1
```

### Authentication
```
Authorization: Bearer YOUR_API_KEY
```

---

## ✨ Features

- ✅ OpenAI-compatible API
- ✅ Multiple AI providers (Anthropic, Google, OpenAI, DeepSeek, Meta, Mistral, etc.)
- ✅ Conversation history
- ✅ Streaming support
- ✅ Rate limiting
- ✅ Token counting

---

## 🖥️ IDE & Tools Integration

Works with any tool that supports OpenAI API:

### VS Code Extensions
- **Continue** - Set Base URL to `http://api.kodnastudio.com/v1`
- **Cody** - Configure custom endpoint
- **CodeGPT** - Add custom provider

### Cursor IDE
Settings → Models → Add Custom Model:
- Base URL: `http://api.kodnastudio.com/v1`
- API Key: `sk-kodna-xxxxx`

### LangChain (Python)
```python
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    base_url="http://api.kodnastudio.com/v1",
    api_key="your-api-key",
    model="claude-opus-4-5-20251101"
)

response = llm.invoke("Hello!")
```

---

## 🌊 Streaming Example

### Python
```python
from openai import OpenAI

client = OpenAI(
    base_url="http://api.kodnastudio.com/v1",
    api_key="your-api-key"
)

stream = client.chat.completions.create(
    model="claude-opus-4-5-20251101",
    messages=[{"role": "user", "content": "Tell me a story"}],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

### JavaScript
```javascript
const stream = await client.chat.completions.create({
    model: 'claude-opus-4-5-20251101',
    messages: [{ role: 'user', content: 'Tell me a story' }],
    stream: true
});

for await (const chunk of stream) {
    process.stdout.write(chunk.choices[0]?.delta?.content || '');
}
```

---

## ❓ Request Format

```json
{
    "model": "claude-opus-4-5-20251101",
    "messages": [
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Hello!"}
    ],
    "temperature": 0.7,
    "max_tokens": 1000,
    "stream": false
}
```

## ✅ Response Format

```json
{
    "id": "chatcmpl-abc123",
    "object": "chat.completion",
    "created": 1234567890,
    "model": "claude-opus-4-5-20251101",
    "choices": [{
        "index": 0,
        "message": {
            "role": "assistant",
            "content": "Hello! How can I help you today?"
        },
        "finish_reason": "stop"
    }],
    "usage": {
        "prompt_tokens": 10,
        "completion_tokens": 20,
        "total_tokens": 30
    }
}
```

---

## 📞 Get Your API Key

Contact us to get your API key: `sk-kodna-xxxxx`

---

© 2025 Kodna Studio. All rights reserved.
