# Day 2 - LLM Models Comparison & Local LLM via Ollama
📅 Date: 25 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. Two Categories of LLM Models

| Closed Source (Paid)  | Open Source (Free)     |
|-----------------------|------------------------|
| GPT-4o (OpenAI)       | Mistral                |
| Claude (Anthropic)    | LLaMA 3 (Meta)         |
| Gemini (Google)       | DeepSeek               |
| Grok (xAI)            | Phi-3 (Microsoft)      |

---

## 2. Closed Source Models

### GPT-4o — by OpenAI
- Best all-round general purpose model
- Excellent at writing, coding, and reasoning
- Supports text, image, and voice input
- Largest plugin and tool ecosystem
- Most popular model in the world
- Weakness: Expensive API, data sent to OpenAI

> Real QA Example:
> Need to write 50 Playwright automation scripts.
> Paste each component into GPT-4o →
> Get working scripts instantly.
> Best for general automation code generation.

---

### Claude 3.5 Sonnet — by Anthropic
- Largest context window: 200,000 tokens
- Best for analyzing long documents
- Very detailed and structured responses
- Strong focus on safety and accuracy
- Weakness: Fewer integrations than ChatGPT

> Real QA Example:
> Client sends 120-page SRS document.
> Paste entire document into Claude →
> Claude reads all 120 pages in one prompt →
> Generates test cases for every single feature.
> Nothing gets cut off. No feature missed.

---

### Gemini 1.5 Pro — by Google
- Largest context window of all: 1 million tokens
- Deep integration with Google Workspace
- Works directly with Google Docs, Sheets, Drive
- Free tier is very generous
- Weakness: Reasoning not as strong as GPT or Claude

> Real QA Example:
> Your team stores test cases in Google Sheets
> and requirements in Google Docs.
> Gemini reads your Google Doc directly →
> generates test cases into your Google Sheet.
> No copy-pasting. Everything stays in Workspace.

---

### DeepSeek — by DeepSeek AI
- Very strong coding and technical reasoning
- Extremely low API cost compared to GPT
- Open source version freely available
- Weakness: Data privacy concern (servers in China)

> Real QA Example:
> Need 50 automation scripts via API.
> GPT-4o API cost: ~$0.75 total
> DeepSeek API cost: ~$0.025 total
> Savings: 97% cheaper for same quality output.
> Best for teams automating at large scale.

---

## 3. Open Source Models

Open Source = model is publicly available.
Anyone can download, run, and modify it for free.
No data sent to any company server.

### Mistral 7B
- Very fast and lightweight
- Runs on a normal laptop (8GB RAM)
- Great for coding and instruction following
- Best for: Local testing, privacy-sensitive projects

### LLaMA 3 — by Meta
- Best open source model available today
- LLaMA 3 70B rivals GPT-4 in many tasks
- Runs locally via Ollama
- Best for: General tasks, building custom AI tools

### Phi-3 — by Microsoft
- Extremely small but surprisingly powerful
- Runs on very low-spec machines (4GB RAM)
- Best for: Low-resource machines, quick tasks

---

## 4. LLM Comparison Sheet

| Feature          | GPT-4o      | Claude 3.5  | Gemini 1.5  | DeepSeek    | Mistral 7B  |
|------------------|-------------|-------------|-------------|-------------|-------------|
| Made By          | OpenAI      | Anthropic   | Google      | DeepSeek AI | Mistral AI  |
| Context Window   | 128k tokens | 200k tokens | 1M tokens   | 64k tokens  | 32k tokens  |
| Best At          | General     | Documents   | Google Apps | Coding      | Speed       |
| Coding Skill     | ⭐⭐⭐⭐⭐   | ⭐⭐⭐⭐      | ⭐⭐⭐        | ⭐⭐⭐⭐⭐   | ⭐⭐⭐        |
| Reasoning        | ⭐⭐⭐⭐⭐   | ⭐⭐⭐⭐⭐    | ⭐⭐⭐⭐      | ⭐⭐⭐⭐      | ⭐⭐⭐        |
| Free Tier        | Limited     | Yes         | Yes         | Yes         | Fully Free  |
| API Cost         | High        | Medium      | Medium      | Very Low    | Free        |
| Data Privacy     | Low         | Medium      | Low         | Very Low    | High ✅     |
| Runs Locally     | ❌          | ❌          | ❌          | ✅          | ✅          |
| Open Source      | ❌          | ❌          | ❌          | ✅          | ✅          |

---

## 5. Which Model to Use — Decision Guide

| Situation                              | Best Model       |
|----------------------------------------|------------------|
| Reviewing 100-page requirement doc     | Claude 3.5       |
| Writing Selenium/Playwright scripts    | GPT-4o/DeepSeek  |
| Team uses Google Docs for test plans   | Gemini 1.5 Pro   |
| Need low cost API for bulk test gen    | DeepSeek         |
| Client data is confidential (NDA)      | Ollama + Mistral |
| Working offline without internet       | Ollama + Mistral |
| Quick test case on free tier           | Claude / Gemini  |

---

## 6. Local LLM via Ollama

### What is Ollama?
Ollama = Free tool to run LLM models on your
own computer — completely offline.

- No internet required after download
- No data sent to any external server
- 100% private and free to use forever

### Why Use Ollama for QA?
- Test AI features without any API cost
- Keep client data private and secure
- Work offline during travel or no wifi
- Build and test AI automation locally

### System Requirements
| Component | Minimum    | Recommended  |
|-----------|------------|--------------|
| RAM       | 8 GB       | 16 GB        |
| Storage   | 10 GB free | 20 GB free   |
| OS        | Win/Mac/Linux | Any       |

---

### Step 1: Install Ollama

# Mac / Linux:
curl -fsSL https://ollama.com/install.sh | sh

# Windows:
Download from https://ollama.com and run .exe

# Verify:
ollama --version

---

### Step 2: Download and Run Models

# Best for beginners:
ollama run mistral

# Best for coding tasks:
ollama run deepseek-coder

# Best overall open source:
ollama run llama3

# Smallest and fastest:
ollama run phi3

# See all downloaded models:
ollama list

# Remove a model:
ollama rm mistral

---

### Step 3: Ask QA Questions in Terminal

After running "ollama run mistral":
>>> Write test cases for login functionality
>>> Review this API test script for errors
>>> Generate boundary value test cases for age field

Type /bye to exit.

---

### Step 4: Connect Ollama to n8n / Langflow

Ollama runs a local API automatically.
Address: http://localhost:11434

# Test it:
curl http://localhost:11434/api/generate \
  -d '{
    "model": "mistral",
    "prompt": "Write a test case for login page",
    "stream": false
  }'

Connect this URL in n8n to build free,
private, automated QA workflows.

---

### Model Size Guide

| Model          | Size  | RAM Needed | Speed  |
|----------------|-------|------------|--------|
| phi3           | ~2 GB | 4 GB       | Fast   |
| mistral        | ~4 GB | 8 GB       | Fast   |
| deepseek-coder | ~4 GB | 8 GB       | Fast   |
| llama3 (8B)    | ~5 GB | 8 GB       | Medium |

Recommended for beginners: Start with mistral

---

> Real QA Example — Private Client:
> You are testing a healthcare app with
> confidential patient data.
> ChatGPT / Claude send data to their servers
> → violates HIPAA and client NDA.
> Ollama + Mistral: everything runs on YOUR laptop.
> Data never leaves your machine.
> Fully compliant. Completely free.

---

## 7. Day 2 Summary

| Topic             | Key Takeaway                                      |
|-------------------|---------------------------------------------------|
| GPT-4o            | Best general model, highest ecosystem             |
| Claude 3.5        | Best for long documents, 200k context window      |
| Gemini 1.5 Pro    | Best for Google Workspace integration             |
| DeepSeek          | Best for coding, 97% cheaper API                  |
| Open Source       | Free, private, run locally via Ollama             |
| Ollama            | Run LLMs on your own laptop — free and offline    |
| Best Starter      | ollama run mistral                                |

---

## 8. Practice Tasks

- [x] Install Ollama on your machine
- [x] Run: ollama run mistral
- [x] Ask: "Write 5 test cases for a login page"
- [x] Run: ollama run deepseek-coder
- [x] Ask: "Write a Selenium test for login button"
- [x] Compare output with ChatGPT or Claude
