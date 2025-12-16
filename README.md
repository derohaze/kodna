# Kodna API Documentation

## 🔑 Public API Key

```
sk-kodna-3c1c64140e3424f044450cb9358dce43ebed79c7c8f4b10a2ac3965ae6ce8864
```

> **Features**: Unlimited usage • 100 req/min rate limit • Completely FREE

---

## 🚀 Quick Start

```python
from openai import OpenAI

client = OpenAI(
    base_url="https://api.kodnastudio.com/v1",
    api_key="sk-kodna-YOUR_API_KEY"
)

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Hello!"}]
)

print(response.choices[0].message.content)
```

---

## 📦 Installation

```bash
# Python
pip install openai

# Node.js
npm install openai

# Go
go get github.com/sashabaranov/go-openai
```

---

## 📚 Available Models

### OpenAI
```
gpt-4o
gpt-4o-mini
gpt-4.1
gpt-3.5-turbo
```

### Anthropic (Claude)
```
claude-opus-4-5-20251101
claude-sonnet-4-5-20250929
claude-haiku-4-5-20251001
```

### Google (Gemini)
```
gemini-2.5-pro
gemini-2.5-flash
gemini-2.0-flash
gemini-1.5-pro
```

### DeepSeek
```
deepseek-v3.2
deepseek-r1-distill-llama-70b
```

### Meta (Llama)
```
llama3.3-70b-instruct
llama3-8b-instruct
```

### Grok (xAI)
```
grok-4.1-fast-reasoning
grok-4.1-fast-non-reasoning
```

### Others
```
qwen/qwen3-next-80b-a3b-instruct
mistralai/mistral-nemotron
moonshotai/kimi-k2-instruct-0905
minimaxai/minimax-m2
```

---

## 🔗 API Reference

### Base URL
```
https://api.kodnastudio.com/v1
```

### Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/v1/chat/completions` | POST | Chat completion |
| `/v1/models` | GET | List models |

---

## ✨ Supported Parameters

All OpenAI-compatible parameters are supported:

```json
{
    "model": "gpt-4o",
    "messages": [
        {"role": "system", "content": "You are helpful."},
        {"role": "user", "content": "Hello!"}
    ],
    "temperature": 0.7,
    "max_tokens": 2048,
    "top_p": 1.0,
    "frequency_penalty": 0.0,
    "presence_penalty": 0.0,
    "stop": ["\n\n"],
    "stream": false,
    "response_format": {"type": "json_object"},
    "tools": [...],
    "tool_choice": "auto"
}
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `model` | string | Model ID |
| `messages` | array | Conversation messages |
| `temperature` | float | Randomness (0.0-2.0) |
| `max_tokens` | int | Max response tokens |
| `top_p` | float | Nucleus sampling (0.0-1.0) |
| `frequency_penalty` | float | Frequency penalty (-2.0 to 2.0) |
| `presence_penalty` | float | Presence penalty (-2.0 to 2.0) |
| `stop` | array | Stop sequences |
| `stream` | bool | Enable streaming |
| `response_format` | object | JSON mode |
| `tools` | array | Function calling |
| `tool_choice` | string | Tool selection |

### Message Roles

| Role | Description |
|------|-------------|
| `user` | User messages |
| `assistant` | AI responses |
| `system` | System instructions |
| `developer` | Auto-converted to `system` |

---

## 🌊 Streaming

```python
stream = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "Tell me a story"}],
    stream=True
)

for chunk in stream:
    if chunk.choices[0].delta.content:
        print(chunk.choices[0].delta.content, end="")
```

---

## 🖼️ Vision (Images)

```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{
        "role": "user",
        "content": [
            {"type": "text", "text": "What's in this image?"},
            {"type": "image_url", "image_url": {"url": "https://example.com/image.jpg"}}
        ]
    }]
)
```

---

## 🔧 Function Calling

```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{"role": "user", "content": "What's the weather in Cairo?"}],
    tools=[{
        "type": "function",
        "function": {
            "name": "get_weather",
            "description": "Get weather for a location",
            "parameters": {
                "type": "object",
                "properties": {
                    "location": {"type": "string"}
                },
                "required": ["location"]
            }
        }
    }]
)
```

---

## 📝 Response Format

```json
{
    "id": "chatcmpl-abc123",
    "object": "chat.completion",
    "created": 1234567890,
    "model": "gpt-4o",
    "choices": [{
        "index": 0,
        "message": {
            "role": "assistant",
            "content": "Hello! How can I help you?"
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

## 💻 Code Examples

### JavaScript
```javascript
import OpenAI from 'openai';

const client = new OpenAI({
    baseURL: 'https://api.kodnastudio.com/v1',
    apiKey: 'sk-kodna-YOUR_API_KEY'
});

const response = await client.chat.completions.create({
    model: 'gpt-4o',
    messages: [{ role: 'user', content: 'Hello!' }]
});

console.log(response.choices[0].message.content);
```

### cURL
```bash
curl https://api.kodnastudio.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-kodna-YOUR_API_KEY" \
  -d '{
    "model": "gpt-4o",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

### Go
```go
config := openai.DefaultConfig("sk-kodna-YOUR_API_KEY")
config.BaseURL = "https://api.kodnastudio.com/v1"
client := openai.NewClientWithConfig(config)

resp, _ := client.CreateChatCompletion(
    context.Background(),
    openai.ChatCompletionRequest{
        Model: "gpt-4o",
        Messages: []openai.ChatCompletionMessage{
            {Role: "user", Content: "Hello!"},
        },
    },
)
fmt.Println(resp.Choices[0].Message.Content)
```

---

## 🖥️ IDE Integration

### Cursor IDE

> ⚠️ **Important**: Cursor requires a **Pro subscription** to use custom API endpoints.

1. Open Cursor Settings (`Ctrl+,` or `Cmd+,`)
2. Go to **Models** section
3. Click **Add Model**
4. Configure:
   - **Model Name**: `gpt-4o` (or any model from the list)
   - **Base URL**: `https://api.kodnastudio.com/v1`
   - **API Key**: `sk-kodna-YOUR_API_KEY`
5. Click **Save**
6. Select the model from the model dropdown in chat

**Supported Models in Cursor:**
```
gpt-4o
claude-opus-4-5-20251101
gemini-2.5-pro
```

### VS Code (Continue Extension)

1. Install **Continue** extension from VS Code marketplace
2. Open config: `Ctrl+Shift+P` → `Continue: Open config.yaml`
3. Add configuration:

```yaml
models:
  - name: Claude Opus
    provider: openai
    model: claude-opus-4-5-20251101
    apiBase: https://api.kodnastudio.com/v1
    apiKey: sk-kodna-YOUR_API_KEY
    roles:
      - chat
      - edit
      - apply
```

4. Save and reload VS Code
5. Open Continue chat with `Ctrl+L`

### Cody (VS Code)

1. Install **Cody** extension
2. Open Settings → Cody
3. Set custom endpoint:
   - **Endpoint**: `https://api.kodnastudio.com/v1`
   - **API Key**: `sk-kodna-YOUR_API_KEY`

### Other IDEs

Any IDE that supports OpenAI API can use Kodna:
- **JetBrains IDEs** (with AI Assistant plugin)
- **Neovim** (with ChatGPT.nvim)
- **Emacs** (with gptel)

---

## 🤖 Automation Tools Integration

### n8n

1. Add **HTTP Request** node
2. Configure:
   - **Method**: `POST`
   - **URL**: `https://api.kodnastudio.com/v1/chat/completions`
   - **Authentication**: `Generic Credential Type`
   - **Header**: `Authorization` = `Bearer sk-kodna-YOUR_API_KEY`
   - **Body Content Type**: `JSON`
   - **Body**:
```json
{
  "model": "gpt-4o",
  "messages": [
    {"role": "user", "content": "{{ $json.message }}"}
  ]
}
```
3. Parse response: `{{ $json.choices[0].message.content }}`

### Zapier

1. Create new Zap
2. Add **Webhooks by Zapier** → **POST**
3. Configure:
   - **URL**: `https://api.kodnastudio.com/v1/chat/completions`
   - **Headers**:
     ```
     Authorization: Bearer sk-kodna-YOUR_API_KEY
     Content-Type: application/json
     ```
   - **Data**:
```json
{
  "model": "gpt-4o",
  "messages": [{"role": "user", "content": "Hello!"}]
}
```

### Make (Integromat)

1. Add **HTTP > Make a Request** module
2. Configure:
   - **URL**: `https://api.kodnastudio.com/v1/chat/completions`
   - **Method**: `POST`
   - **Headers**:
     ```
     Authorization: Bearer sk-kodna-YOUR_API_KEY
     Content-Type: application/json
     ```
   - **Body**:
```json
{
  "model": "gpt-4o",
  "messages": [{"role": "user", "content": "{{1.message}}"}]
}
```

### Power Automate

1. Add **HTTP** action
2. Configure:
   - **Method**: `POST`
   - **URI**: `https://api.kodnastudio.com/v1/chat/completions`
   - **Headers**:
     ```
     Authorization: Bearer sk-kodna-YOUR_API_KEY
     Content-Type: application/json
     ```
   - **Body**:
```json
{
  "model": "gpt-4o",
  "messages": [{"role": "user", "content": "@{triggerBody()['message']}"}]
}
```

### LangChain (Python)

```python
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    base_url="https://api.kodnastudio.com/v1",
    api_key="sk-kodna-YOUR_API_KEY",
    model="gpt-4o"
)

response = llm.invoke("Hello!")
print(response.content)
```

### LangChain (JavaScript)

```javascript
import { ChatOpenAI } from "@langchain/openai";

const llm = new ChatOpenAI({
    modelName: "gpt-4o",
    configuration: {
        baseURL: "https://api.kodnastudio.com/v1",
        apiKey: "sk-kodna-YOUR_API_KEY"
    }
});

const response = await llm.invoke("Hello!");
console.log(response.content);
```

### Google Apps Script

```javascript
function callKodnaAPI(message) {
  const url = 'https://api.kodnastudio.com/v1/chat/completions';
  
  const payload = {
    model: 'gpt-4o',
    messages: [{ role: 'user', content: message }]
  };
  
  const options = {
    method: 'post',
    contentType: 'application/json',
    headers: {
      'Authorization': 'Bearer sk-kodna-YOUR_API_KEY'
    },
    payload: JSON.stringify(payload)
  };
  
  const response = UrlFetchApp.fetch(url, options);
  const data = JSON.parse(response.getContentText());
  return data.choices[0].message.content;
}
```

### Any HTTP Client

Since Kodna API is REST-based, it works with any tool:

```
POST https://api.kodnastudio.com/v1/chat/completions
Headers:
  Authorization: Bearer sk-kodna-YOUR_API_KEY
  Content-Type: application/json
Body:
  {"model": "gpt-4o", "messages": [{"role": "user", "content": "Hello!"}]}
```

---

## ⚠️ Notes

- Models may occasionally experience downtime and automatically recover
- Large requests (>60K chars) are automatically compressed
- Rate limit: 100 requests/minute (public key)

---

© 2025 Kodna Studio
