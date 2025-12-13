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
| Model | Description |
|-------|-------------|
| `claude-opus-4-5-20251101` | Latest Claude Opus - Most capable ⭐ |
| `claude-opus-4-1-20250805` | Claude Opus 4.1 |
| `claude-sonnet-4-5-20250929` | Latest Claude Sonnet |
| `claude-sonnet-4-20250514` | Claude Sonnet 4 |
| `claude-haiku-4-5-20251001` | Fast Claude Haiku |

### OpenAI / GPT
| Model | Description |
|-------|-------------|
| `gpt-5.1` | Enhanced GPT-5 ⭐ |
| `gpt-5` | Latest GPT-5 |
| `gpt-4.1` | Enhanced GPT-4 |
| `gpt-4o` | Optimized GPT-4 |
| `gpt-4o-mini` | Fast GPT-4o variant |
| `gpt-3.5-turbo` | Fast and reliable |
| `openai-gpt-oss-20b` | Open source GPT 20B |
| `openai-gpt-oss-120b` | Large open source GPT 120B |

### Google / Gemini
| Model | Description |
|-------|-------------|
| `gemini-2.5-pro` | Latest Gemini Pro ⭐ |
| `gemini-2.5-flash` | Fast Gemini model |
| `gemini-2.0-flash` | Previous gen fast |
| `gemini-1.5-pro` | Stable Gemini Pro |
| `gemini-1.5-flash` | Fast Gemini 1.5 |
| `gemini-pro` | Original Gemini Pro |

### DeepSeek
| Model | Description |
|-------|-------------|
| `deepseek-v3.2` | Enhanced DeepSeek |
| `deepseek-ai/deepseek-v3.1` | Latest DeepSeek |
| `deepseek-ai/deepseek-v3.1-terminus` | Terminus variant |
| `deepseek-r1-distill-llama-70b` | R1 Distilled model |

### Qwen / Alibaba
| Model | Description |
|-------|-------------|
| `qwen/qwen3-next-80b-a3b-instruct` | Large Qwen model |

### Mistral AI
| Model | Description |
|-------|-------------|
| `mistralai/mistral-nemotron` | Mistral Nemotron |

### Meta / Llama
| Model | Description |
|-------|-------------|
| `llama3.3-70b-instruct` | Large Llama model |
| `llama3-8b-instruct` | Small Llama model |

### Moonshot AI
| Model | Description |
|-------|-------------|
| `moonshotai/kimi-k2-instruct-0905` | Moonshot Kimi model |

### Minimax
| Model | Description |
|-------|-------------|
| `minimaxai/minimax-m2` | Minimax model |

### Grok / xAI
| Model | Description |
|-------|-------------|
| `grok-4.1-fast-reasoning` | Fast reasoning Grok |
| `grok-4.1-fast-non-reasoning` | Fast non-reasoning Grok |

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

## 📞 Get Your API Key

Contact us to get your API key: `sk-kodna-xxxxx`

---

© 2025 Kodna Studio. All rights reserved.
