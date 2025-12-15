# Kodna API Documentation

## 🔑 Public API Key

```
sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
```

> **💡 Public Key Features**:
> - ✅ **Unlimited usage** - No consumption limits
> - ⚠️ **Rate Limit**: 100 requests per minute
> - 🆓 **Completely FREE** - No payment required

---

> **⚠️ Important Notes**:
> - Models may occasionally experience downtime and automatically recover. This is normal behavior.
> - This service is completely **FREE** - no payment required.

---

## 🚀 Quick Start

Get started with Kodna API in seconds. Our API is fully compatible with OpenAI's SDK.

---

## 📦 Installation

> **📌 Note**: Python and JavaScript/Node.js are **official** OpenAI SDKs. Other languages use **community-maintained** SDKs that are compatible with OpenAI API format.

### Python (Official)
```bash
pip install openai
```

### JavaScript / Node.js (Official)
```bash
npm install openai
```

### Go
```bash
go get github.com/sashabaranov/go-openai
```

### Java
```xml
<!-- Add to pom.xml -->
<dependency>
    <groupId>com.theokanning.openai-gpt3-java</groupId>
    <artifactId>service</artifactId>
    <version>0.18.2</version>
</dependency>
```

### C# / .NET
```bash
dotnet add package OpenAI
```

### PHP
```bash
composer require openai-php/client
```

### Ruby
```bash
gem install ruby-openai
```

### Rust
```toml
# Add to Cargo.toml
[dependencies]
openai = "1.0.0"
```

### Swift
```swift
// Add to Package.swift
dependencies: [
    .package(url: "https://github.com/MacPaw/OpenAI.git", from: "0.2.0")
]
```

---

## 🔑 Usage Examples

### Python
```python
from openai import OpenAI

client = OpenAI(
    base_url="http://api.kodnastudio.com/v1",
    api_key="sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a"
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
    apiKey: 'sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a'
});

const response = await client.chat.completions.create({
    model: 'claude-opus-4-5-20251101',
    messages: [{ role: 'user', content: 'Hello!' }]
});

console.log(response.choices[0].message.content);
```

### Go
```go
package main

import (
    "context"
    "fmt"
    openai "github.com/sashabaranov/go-openai"
)

func main() {
    config := openai.DefaultConfig("sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a")
    config.BaseURL = "http://api.kodnastudio.com/v1"
    client := openai.NewClientWithConfig(config)

    resp, err := client.CreateChatCompletion(
        context.Background(),
        openai.ChatCompletionRequest{
            Model: "claude-opus-4-5-20251101",
            Messages: []openai.ChatCompletionMessage{
                {
                    Role:    openai.ChatMessageRoleUser,
                    Content: "Hello!",
                },
            },
        },
    )

    if err != nil {
        fmt.Printf("Error: %v\n", err)
        return
    }

    fmt.Println(resp.Choices[0].Message.Content)
}
```

### Java
```java
import com.theokanning.openai.completion.chat.ChatCompletionRequest;
import com.theokanning.openai.completion.chat.ChatMessage;
import com.theokanning.openai.service.OpenAiService;

import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        OpenAiService service = new OpenAiService(
            "sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a",
            Duration.ofSeconds(30),
            "http://api.kodnastudio.com/v1"
        );

        ChatCompletionRequest chatRequest = ChatCompletionRequest.builder()
            .model("claude-opus-4-5-20251101")
            .messages(Arrays.asList(
                new ChatMessage("user", "Hello!")
            ))
            .build();

        System.out.println(service.createChatCompletion(chatRequest)
            .getChoices().get(0).getMessage().getContent());
    }
}
```

### C# / .NET
```csharp
using OpenAI;
using OpenAI.Chat;

var client = new OpenAIClient(
    new OpenAIAuthentication("sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a"),
    new OpenAIClientSettings("api.kodnastudio.com")
);

var chatPrompts = new List<ChatPrompt>
{
    new ChatPrompt("user", "Hello!")
};

var chatRequest = new ChatCompletionRequest(chatPrompts, model: "claude-opus-4-5-20251101");
var result = await client.ChatEndpoint.GetCompletionAsync(chatRequest);

Console.WriteLine(result.FirstChoice.Message.Content);
```

### PHP
```php
<?php

require 'vendor/autoload.php';

use OpenAI\Client;

$client = Client::factory()
    ->withBaseUri('http://api.kodnastudio.com/v1')
    ->withHttpHeader('Authorization', 'Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a')
    ->make();

$response = $client->chat()->create([
    'model' => 'claude-opus-4-5-20251101',
    'messages' => [
        ['role' => 'user', 'content' => 'Hello!'],
    ],
]);

echo $response->choices[0]->message->content;
```

### Ruby
```ruby
require 'ruby/openai'

client = OpenAI::Client.new(
    access_token: 'sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a',
    uri_base: 'http://api.kodnastudio.com/v1'
)

response = client.chat(
    parameters: {
        model: 'claude-opus-4-5-20251101',
        messages: [
            { role: 'user', content: 'Hello!' }
        ]
    }
)

puts response.dig('choices', 0, 'message', 'content')
```

### Rust
```rust
use openai::chat::{ChatCompletion, Message, Role};
use openai::Client;

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let client = Client::new()
        .with_api_key("sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a")
        .with_base_url("http://api.kodnastudio.com/v1");

    let request = ChatCompletion::builder("claude-opus-4-5-20251101")
        .add_message(Message {
            role: Role::User,
            content: "Hello!".to_string(),
        })
        .build();

    let response = client.chat().create(request).await?;
    println!("{}", response.choices[0].message.content);

    Ok(())
}
```

### Swift
```swift
import OpenAI

let client = OpenAI(apiToken: "sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a")
client.baseURL = "http://api.kodnastudio.com/v1"

let query = ChatQuery(
    model: "claude-opus-4-5-20251101",
    messages: [
        .init(role: .user, content: "Hello!")
    ]
)

do {
    let result = try await client.chats(query: query)
    print(result.choices[0].message.content ?? "")
} catch {
    print("Error: \(error)")
}
```

### Other Languages

Since Kodna API is a **REST API**, you can use it with **any language** that supports HTTP requests:

- **Dart / Flutter**: Use `http` package
- **Kotlin**: Use `OkHttp` or `Ktor`
- **C / C++**: Use `libcurl` or `cpp-httplib`
- **Lua**: Use `lua-http` or `luasocket`
- **Perl**: Use `LWP::UserAgent` or `HTTP::Tiny`
- **Dart**: Use `http` package
- **Any language**: Make HTTP POST request to `/v1/chat/completions`

### cURL / Bash
```bash
curl http://api.kodnastudio.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a" \
  -d '{
    "model": "claude-opus-4-5-20251101",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

---

## 📚 Available Models

### Anthropic / Claude

| Model ID | Context | Output |
|----------|--------|--------|
| `claude-opus-4-5-20251101` | 200K | 64K |
| `claude-opus-4-1-20250805` | 80K | 32K |
| `claude-sonnet-4-5-20250929` | 200K | 64K |
| `claude-sonnet-4-20250514` | 128K | 64K |
| `claude-haiku-4-5-20251001` | 200K | 32K |

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

| Model ID | Context | Output |
|----------|--------|--------|
| `gpt-5.1` | 128K | 64K |
| `gpt-5` | 128K | 64K |
| `gpt-4.1` | 128K | 16K |
| `gpt-4o` | 128K | 4K |
| `gpt-4o-mini` | 128K | 4K |
| `gpt-3.5-turbo` | 16K | 4K |
| `openai-gpt-oss-20b` | 128K | 128K |
| `openai-gpt-oss-120b` | 128K | 128K |

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

| Model ID | Context | Output |
|----------|--------|--------|
| `gemini-3-pro-preview` | 200K | 64K |
| `gemini-2.5-pro` | 128K | 64K |
| `gemini-2.5-flash` | 196K | 32K |
| `gemini-2.0-flash` | 128K | 64K |
| `gemini-1.5-pro` | 128K | 64K |
| `gemini-1.5-flash` | 128K | 64K |
| `gemini-pro` | 128K | 64K |

<details>
<summary>📋 Copy Model IDs</summary>

```
gemini-3-pro-preview
gemini-2.5-pro
gemini-2.5-flash
gemini-2.0-flash
gemini-1.5-pro
gemini-1.5-flash
gemini-pro
```

</details>

### DeepSeek

| Model ID | Context | Output |
|----------|--------|--------|
| `deepseek-v3.2` | 128K | 64K |
| `deepseek-ai/deepseek-v3.1` | 128K | 16K |
| `deepseek-ai/deepseek-v3.1-terminus` | 164K | 56K |
| `deepseek-r1-distill-llama-70b` | 128K | 128K |

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

| Model ID | Context | Output |
|----------|--------|--------|
| `qwen/qwen3-next-80b-a3b-instruct` | 262K | 16K |

<details>
<summary>📋 Copy Model ID</summary>

```
qwen/qwen3-next-80b-a3b-instruct
```

</details>

### Mistral AI

| Model ID | Context | Output |
|----------|--------|--------|
| `mistralai/mistral-nemotron` | 128K | 16K |

<details>
<summary>📋 Copy Model ID</summary>

```
mistralai/mistral-nemotron
```

</details>

### Meta / Llama

| Model ID | Context | Output |
|----------|--------|--------|
| `llama3.3-70b-instruct` | 131K | 131K |
| `llama3-8b-instruct` | 8K | 8K |

<details>
<summary>📋 Copy Model IDs</summary>

```
llama3.3-70b-instruct
llama3-8b-instruct
```

</details>

### Moonshot AI

| Model ID | Context | Output |
|----------|--------|--------|
| `moonshotai/kimi-k2-instruct-0905` | 256K | 56K |

<details>
<summary>📋 Copy Model ID</summary>

```
moonshotai/kimi-k2-instruct-0905
```

</details>

### Minimax

| Model ID | Context | Output |
|----------|--------|--------|
| `minimaxai/minimax-m2` | 128K | 32K |

<details>
<summary>📋 Copy Model ID</summary>

```
minimaxai/minimax-m2
```

</details>

### Grok / xAI

| Model ID | Context | Output |
|----------|--------|--------|
| `grok-4.1-fast-reasoning` | 200K | 64K |
| `grok-4.1-fast-non-reasoning` | 200K | 64K |

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
Authorization: Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
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

## 🤖 Automation Tools Integration

Kodna API is **100% compatible** with OpenAI API format, so it works seamlessly with **any automation tool** that supports OpenAI:

### n8n

1. Add **HTTP Request** node
2. Configure:
   - **Method**: `POST`
   - **URL**: `http://api.kodnastudio.com/v1/chat/completions`
   - **Authentication**: `Generic Credential Type`
   - **Header Name**: `Authorization`
   - **Header Value**: `Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a`
   - **Body Content Type**: `JSON`
   - **Body**: 
   ```json
   {
     "model": "claude-opus-4-5-20251101",
     "messages": [
       {"role": "user", "content": "{{ $json.message }}"}
     ]
   }
   ```
3. Parse response: `{{ $json.choices[0].message.content }}`

### Zapier

1. Create new Zap
2. Add **Webhooks by Zapier** → **POST** action
3. Configure:
   - **URL**: `http://api.kodnastudio.com/v1/chat/completions`
   - **Method**: `POST`
   - **Headers**: 
     ```
     Authorization: Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
     Content-Type: application/json
     ```
   - **Data**: 
   ```json
   {
     "model": "claude-opus-4-5-20251101",
     "messages": [{"role": "user", "content": "Hello from Zapier!"}]
   }
   ```

### Make (Integromat)

1. Add **HTTP > Make a Request** module
2. Configure:
   - **URL**: `http://api.kodnastudio.com/v1/chat/completions`
   - **Method**: `POST`
   - **Headers**:
     ```
     Authorization: Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
     Content-Type: application/json
     ```
   - **Body Type**: `Raw`
   - **Body**: 
   ```json
   {
     "model": "claude-opus-4-5-20251101",
     "messages": [{"role": "user", "content": "{{1.message}}"}]
   }
   ```

### Microsoft Power Automate

1. Add **HTTP** action
2. Configure:
   - **Method**: `POST`
   - **URI**: `http://api.kodnastudio.com/v1/chat/completions`
   - **Headers**:
     ```
     Authorization: Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
     Content-Type: application/json
     ```
   - **Body**:
   ```json
   {
     "model": "claude-opus-4-5-20251101",
     "messages": [{"role": "user", "content": "@{triggerBody()['message']}"}]
   }
   ```

### IFTTT

1. Use **Webhooks** service
2. Configure:
   - **URL**: `http://api.kodnastudio.com/v1/chat/completions`
   - **Method**: `POST`
   - **Content Type**: `application/json`
   - **Body**:
   ```json
   {
     "model": "claude-opus-4-5-20251101",
     "messages": [{"role": "user", "content": "{{Value1}}"}],
     "headers": {
       "Authorization": "Bearer sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a"
     }
   }
   ```

### Google Apps Script

```javascript
function callKodnaAPI(message) {
  const url = 'http://api.kodnastudio.com/v1/chat/completions';
  const apiKey = 'sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a';
  
  const payload = {
    model: 'claude-opus-4-5-20251101',
    messages: [
      { role: 'user', content: message }
    ]
  };
  
  const options = {
    method: 'post',
    contentType: 'application/json',
    headers: {
      'Authorization': 'Bearer ' + apiKey
    },
    payload: JSON.stringify(payload)
  };
  
  const response = UrlFetchApp.fetch(url, options);
  const data = JSON.parse(response.getContentText());
  return data.choices[0].message.content;
}
```

### Other Automation Tools

Since Kodna API uses **standard OpenAI API format**, it works with:
- ✅ **Any tool that supports OpenAI API**
- ✅ **Any HTTP client** (Postman, Insomnia, etc.)
- ✅ **Any programming language** with HTTP support
- ✅ **Any workflow automation platform**

**Key Configuration for All Tools:**
- **Base URL**: `http://api.kodnastudio.com/v1`
- **Endpoint**: `/chat/completions`
- **Method**: `POST`
- **Authentication**: `Bearer {your-api-key}`
- **Content-Type**: `application/json`

---

## 🖥️ IDE & Tools Integration

Works with any tool that supports OpenAI API:

### Continue Extension (VS Code)

1. Install **Continue** extension from VS Code marketplace
2. Open Continue config: `Ctrl+Shift+P` → `Continue: Open config.yaml`
3. Add this configuration:

```yaml
name: Local Config
version: 1.0.0
schema: v1
models:
  - name: Claude Opus 4.5
    provider: openai
    model: claude-opus-4-5-20251101
    apiBase: http://api.kodnastudio.com/v1
    apiKey: sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
    roles:
      - chat
      - edit
      - apply
```

4. Save and reload VS Code (`Ctrl+Shift+P` → `Reload Window`)
5. Open Continue chat with `Ctrl+L` and start using!

**Available Models**: Use any model ID from the [Available Models](#-available-models) section above.

### Cursor IDE
Settings → Models → Add Custom Model:
- Base URL: `http://api.kodnastudio.com/v1`
- API Key: `sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a`

### VS Code Extensions
- **Cody** - Configure custom endpoint
- **CodeGPT** - Add custom provider

### LangChain (Python)
```python
from langchain_openai import ChatOpenAI

llm = ChatOpenAI(
    base_url="http://api.kodnastudio.com/v1",
    api_key="sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a",
    model="claude-opus-4-5-20251101"
)

response = llm.invoke("Hello!")
```

### LangChain (JavaScript)
```javascript
import { ChatOpenAI } from "@langchain/openai";

const llm = new ChatOpenAI({
    modelName: "claude-opus-4-5-20251101",
    configuration: {
        baseURL: "http://api.kodnastudio.com/v1",
        apiKey: "sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a"
    }
});

const response = await llm.invoke("Hello!");
console.log(response.content);
```

---

## 🌊 Streaming Example

### Python
```python
from openai import OpenAI

client = OpenAI(
    base_url="http://api.kodnastudio.com/v1",
    api_key="sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a"
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

### Go (Streaming)
```go
stream, err := client.CreateChatCompletionStream(
    context.Background(),
    openai.ChatCompletionRequest{
        Model: "claude-opus-4-5-20251101",
        Messages: []openai.ChatCompletionMessage{
            {Role: openai.ChatMessageRoleUser, Content: "Tell me a story"},
        },
        Stream: true,
    },
)

if err != nil {
    fmt.Printf("Error: %v\n", err)
    return
}

defer stream.Close()

for {
    response, err := stream.Recv()
    if errors.Is(err, io.EOF) {
        break
    }
    if err != nil {
        fmt.Printf("Error: %v\n", err)
        break
    }
    fmt.Print(response.Choices[0].Delta.Content)
}
```

### C# / .NET (Streaming)
```csharp
var chatRequest = new ChatCompletionRequest(
    chatPrompts,
    model: "claude-opus-4-5-20251101",
    temperature: 0.7f
);

await foreach (var result in client.ChatEndpoint.StreamCompletionAsync(chatRequest))
{
    Console.Write(result.FirstChoice.Message.Content);
}
```

### PHP (Streaming)
```php
$stream = $client->chat()->createStreamed([
    'model' => 'claude-opus-4-5-20251101',
    'messages' => [
        ['role' => 'user', 'content' => 'Tell me a story'],
    ],
]);

foreach ($stream as $response) {
    echo $response->choices[0]->delta->content ?? '';
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

### Public API Key

You can use this public API key to get started:

```
sk-kodna-649a05aef37df2691583ea137da5654d5f494131cab5d04c0a05a01695861a7a
```

### Custom API Key

Contact us to get your custom API key: `sk-kodna-xxxxx`

---

© 2025 Kodna Studio. All rights reserved.
