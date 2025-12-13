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
| Model |
|-------|
| `claude-opus-4-5-20251101` ⭐ |
| `claude-opus-4-1-20250805` |
| `claude-sonnet-4-5-20250929` |
| `claude-sonnet-4-20250514` |
| `claude-haiku-4-5-20251001` |

### OpenAI / GPT
| Model |
|-------|
| `gpt-5.1` ⭐ |
| `gpt-5` |
| `gpt-4.1` |
| `gpt-4o` |
| `gpt-4o-mini` |
| `gpt-3.5-turbo` |
| `openai-gpt-oss-20b` |
| `openai-gpt-oss-120b` |

### Google / Gemini
| Model |
|-------|
| `gemini-2.5-pro` ⭐ |
| `gemini-2.5-flash` |
| `gemini-2.0-flash` |
| `gemini-1.5-pro` |
| `gemini-1.5-flash` |
| `gemini-pro` |

### DeepSeek
| Model |
|-------|
| `deepseek-v3.2` |
| `deepseek-ai/deepseek-v3.1` |
| `deepseek-ai/deepseek-v3.1-terminus` |
| `deepseek-r1-distill-llama-70b` |

### Qwen / Alibaba
| Model |
|-------|
| `qwen/qwen3-next-80b-a3b-instruct` |

### Mistral AI
| Model |
|-------|
| `mistralai/mistral-nemotron` |

### Meta / Llama
| Model |
|-------|
| `llama3.3-70b-instruct` |
| `llama3-8b-instruct` |

### Moonshot AI
| Model |
|-------|
| `moonshotai/kimi-k2-instruct-0905` |

### Minimax
| Model |
|-------|
| `minimaxai/minimax-m2` |

### Grok / xAI
| Model |
|-------|
| `grok-4.1-fast-reasoning` |
| `grok-4.1-fast-non-reasoning` |

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

