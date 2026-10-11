# Free AI API Directory — No API Key Required

A curated, **actually-tested** list of free AI APIs you can call today. Many of them need
**no API key at all** — just `curl` and go.

> Maintained by [APIShare.cc](https://apishare.cc?utm_source=github&utm_medium=readme&utm_campaign=free_api_directory) —
> a free API directory and unified gateway for LLM, TTS, embedding and image-generation models.

---

## TL;DR — zero-key endpoints

| Service | Category | Key needed? | Endpoint |
|---|---|---|---|
| Hugging Face Inference | LLM / Text-gen | ❌ No | `https://api-inference.huggingface.co/models/{model}` |
| Ollama (local) | LLM | ❌ No | `http://localhost:11434/api/generate` |
| LM Studio (local) | LLM | ❌ No | `http://localhost:1234/v1/chat/completions` |
| Groq | LLM (fast) | ✅ Free, no card | `https://api.groq.com/openai/v1/chat/completions` |
| Google Gemini | LLM (1M ctx) | ✅ Free, no card | `https://generativelanguage.googleapis.com/v1beta/models` |
| Together AI | LLM / Code | ✅ Free $25 credit | `https://api.together.xyz/v1/chat/completions` |
| OpenRouter | Multi-model | ✅ Free tier | `https://openrouter.ai/api/v1/chat/completions` |

## Quick start — no key, no signup

```bash
curl -X POST "https://api-inference.huggingface.co/models/mistralai/Mistral-7B-Instruct-v0.2" \
  -H "Content-Type: application/json" \
  -d '{"inputs":"Explain what an API gateway is in one sentence."}'
```

```python
import requests

r = requests.post(
    "https://api-inference.huggingface.co/models/mistralai/Mistral-7B-Instruct-v0.2",
    json={"inputs": "Explain what an API gateway is in one sentence."},
    timeout=60,
)
print(r.json())
```

## Local-first: Ollama

```bash
ollama pull llama3.2
curl http://localhost:11434/api/generate \
  -d '{"model":"llama3.2","prompt":"Hello!","stream":false}'
```

Zero network, zero cost, zero key. Best option when your data cannot leave the machine.

## Free-tier cloud: Groq (fastest inference)

```bash
curl https://api.groq.com/openai/v1/chat/completions \
  -H "Authorization: Bearer $GROQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"llama-3.3-70b-versatile","messages":[{"role":"user","content":"Hi"}]}'
```

Registration takes ~20 seconds and asks for no credit card.

## Where to find more

The full directory — including free **TTS**, **embedding**, **OCR** and **image-generation**
endpoints, plus rate limits and latency benchmarks — lives at
[APIShare.cc free API list](https://apishare.cc/free-apis?utm_source=github&utm_medium=readme&utm_campaign=free_api_directory).

There is also a step-by-step tutorial on calling LLMs without any key:
[Free LLM API tutorial (中文)](https://apishare.cc/article/fa-88cfdec1/zh?utm_source=github&utm_medium=readme&utm_campaign=free_api_directory).

## Contributing

Found a free endpoint that is missing, or one that started requiring a key? Open an issue —
every entry here is re-tested before it is listed.

---

*Directory data and unified gateway provided by [APIShare.cc](https://apishare.cc?utm_source=github&utm_medium=readme&utm_campaign=free_api_directory).*
