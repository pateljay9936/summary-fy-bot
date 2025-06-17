# 📄 Summary GPT Bot

An AI-powered Telegram bot that generates **concise summaries** from various content types including text, URLs, PDFs, and YouTube videos.

> ⚠️ Note: YouTube Shorts are **not supported**.

---

## 🚀 Features

- ✅ Summarize **text**
- ✅ Summarize **web URLs**
- ✅ Summarize **PDF documents**
- ✅ Summarize **YouTube videos**

---

## 🛠️ Usage

### 🔐 Personal Usage (OpenAI GPT-4)

Launch the bot **only for you and your friends** using Docker:

```sh
docker run -d \
  -e LLM_MODEL=gpt-4 \
  -e OPENAI_API_KEY=$OPENAI_API_KEY \
  -e TELEGRAM_TOKEN=$YOUR_TG_TOKEN \
  -e TS_LANG=$YOUR_LANGUAGE \
  -e ALLOWED_USERS=<friend1_id>,<friend2_id>,<your_id> \
  tonypai/summary-gpt-bot:latest
```

---

### ☁️ Azure OpenAI Deployment

Launch the bot using **Azure OpenAI**:

```sh
docker run -d \
  -e AZURE_API_BASE=https://<your_azure_resource_name>.openai.azure.com \
  -e AZURE_API_KEY=$AZURE_API_KEY \
  -e AZURE_API_VERSION=2024-02-15-preview \
  -e LLM_MODEL=azure/<your_deployment_name> \
  -e TELEGRAM_TOKEN=$YOUR_TG_TOKEN \
  -e TS_LANG=$YOUR_LANGUAGE \
  tonypai/summary-gpt-bot:latest
```

---

## ⚙️ Environment Variables

### 🔑 LLM Configuration

| Variable            | Description                                 |
|---------------------|---------------------------------------------|
| `AZURE_API_BASE`    | Base URL for Azure OpenAI API               |
| `AZURE_API_KEY`     | Azure OpenAI API key                        |
| `AZURE_API_VERSION` | Azure OpenAI API version                    |
| `OPENAI_API_KEY`    | OpenAI API key                              |
| `LLM_MODEL`         | Model to use (e.g., `gpt-4`, `gpt-3.5-turbo-16k`, or `azure/<deployment_name>`) |

### 🤖 Bot Configuration

| Variable         | Description                                                                          |
|------------------|--------------------------------------------------------------------------------------|
| `TELEGRAM_TOKEN` | Token for accessing Telegram Bot API (**required**)                                  |
| `TS_LANG`        | Language for summaries (default: Taiwanese Mandarin)                                 |
| `CHUNK_SIZE`     | Max tokens per input chunk (default: `10000`)                                        |
| `ALLOWED_USERS`  | Comma-separated list of Telegram user IDs allowed to use the bot *(optional)*        |
| `DDG_REGION`     | [DuckDuckGo region](https://github.com/deedy5/duckduckgo_search#regions) (default: `wt-wt`) |

---

## 🧾 Notes

- To get your Telegram user ID, message [@myidbot](https://t.me/myidbot).
- Summarization works best for English and major languages.
- This bot is designed for **private use** — perfect for study groups, teams, and friends.

---

## 📦 Docker Image

Docker Hub: [jomoporo/summary-gpt-bot](https://hub.docker.com/r/jomoporo/summary-fy-bot)
