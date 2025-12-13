# Kodna API - Quick Start Guide

## 🚀 Get Started in 30 Seconds

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

## 📦 Available Models

| Model | Description |
|-------|-------------|
| `claude-opus-4-5-20251101` | Most capable model |
| `gemini-2.5-pro` | Google's advanced model |
| `gemini-2.5-flash` | Fast responses |

## 🔑 Get Your API Key

Contact us to get your API key: `sk-kodna-xxxxx`

## 📚 API Reference

- **Base URL:** `http://api.kodnastudio.com/v1`
- **Endpoint:** `/chat/completions`
- **Method:** `POST`

## ✨ Features

- ✅ OpenAI-compatible API
- ✅ Multiple AI models
- ✅ Conversation history
- ✅ Streaming support
- ✅ Rate limiting
