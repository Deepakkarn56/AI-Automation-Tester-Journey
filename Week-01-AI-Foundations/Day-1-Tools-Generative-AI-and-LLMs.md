# Day 1 - Tools Overview, Generative AI & LLMs
📅 Date: 24 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. Tools Overview

### AI Tools:

**ChatGPT (by OpenAI)**
- A conversational AI that can generate text,
  write code, and answer questions
- QA Use: Writing test cases, generating bug
  reports, creating automation code

> Real Example: Paste login page requirements →
> ChatGPT generates 7 test cases in 20 seconds.
> 2 hours of manual work done instantly.

**Claude (by Anthropic)**
- An AI assistant best known for analyzing
  long documents and giving detailed explanations
- QA Use: Reviewing test plans, analyzing
  large requirement documents
- Special: Has the largest context window
  among all AI tools (200,000 tokens)

> Real Example: Paste an 80-page BRD →
> Claude reads all of it in one prompt and lists
> every feature that needs test coverage.
> 4 hours of reading done in 5 minutes.

**Gemini (by Google)**
- Google's AI assistant integrated with
  Google Workspace
- QA Use: Works well with Google Docs,
  Sheets, and Drive for QA documentation

> Real Example: Open Gemini inside Google Sheets →
> Ask it to generate test cases directly into the sheet.
> No copy-paste needed.

---

### Automation Tools:

**n8n**
- A workflow automation tool that connects
  different apps and automates repetitive tasks
- QA Use: Automatically create test cases
  when a Jira ticket is raised
- Example Flow:
  Jira Ticket Created → AI generates test cases
  → Test cases saved in Google Sheets

> Real Example:
> Developer creates Jira ticket
> → n8n detects it instantly
> → Sends to ChatGPT → test cases generated
> → Saved to Google Sheets
> → Slack notification sent to tester
> Result: Done in 2 minutes automatically.

**Langflow**
- A visual tool to build AI-powered workflows
  without writing much code
- QA Use: Build AI agents that understand
  requirements and generate test strategies

> Real Example: Build once in Langflow:
> Upload requirement PDF → AI reads it →
> generates full test strategy.
> Share with whole QA team — anyone can use it.

---

### IDEs (Code Editors):

**VS Code**
- Most popular free code editor
- Used for: Writing notes, automation scripts,
  and managing project files

**Cursor**
- VS Code with built-in AI assistance
- Helps write and fix code using AI suggestions

> Real Example: Type comment in Cursor:
> "// test login fails with wrong password"
> → AI auto-suggests full test code below.
> Press Tab to accept. Done in seconds.

---

## 2. What is Generative AI?

### Old AI (Before 2022):
Old AI could only CLASSIFY or PREDICT.
- Input: Photo of a dog or cat?
- Output: "This is a Cat"
- It could only recognize, not create

### Generative AI (After 2022):
Generative AI can CREATE new content from scratch.
- Input: "Write a test case for login page"
- Output: Complete, detailed test case ready!
- It generates something NEW every time

### Why is it called "Generative"?
Because it GENERATES (creates) new content
such as text, images, code, and videos.

### Real World Examples:
| Tool             | What it Generates |
|------------------|-------------------|
| ChatGPT          | Text, Code        |
| Claude           | Text, Analysis    |
| Midjourney       | Images            |
| GitHub Copilot   | Code              |
| Sora             | Videos            |

### Impact on QA Testing:

**Before Generative AI:**
- Tester reads requirements manually
- Tester writes test cases from scratch
- Time taken: 2-3 hours per feature

**After Generative AI:**
- Tester gives requirements to AI
- AI generates test case drafts instantly
- Tester reviews and refines
- Time taken: 20-30 minutes per feature

> Real Example:
> Before: Tester reads 15-page requirement manually,
> writes each test case one by one → 3 hours.
> After: Paste into ChatGPT → 30 test cases in
> 20 seconds → tester reviews → 25 minutes total.

> Key Point: AI does not replace testers.
> It makes testers faster and more efficient.

---

## 3. How LLMs Work

### What is an LLM?
LLM = Large Language Model

| Word     | Meaning                              |
|----------|--------------------------------------|
| Large    | Trained on billions of text data     |
| Language | Understands and generates human text |
| Model    | The AI brain/system                  |

Examples of LLMs: GPT-4, Claude, Gemini, DeepSeek

---

### Concept 1: Tokenization

**What is it?**
When you type something, the LLM does not read
your text as words. It first breaks your text
into smaller pieces called TOKENS.

**Why Tokens?**
Because computers understand numbers, not words.
Each token is converted into a number that
the machine can process.

**Example:**
Input Text: "Write test case for login"

| Token | Number |
|-------|--------|
| Write | 8890   |
| test  | 1332   |
| case  | 1539   |
| for   | 329    |
| login | 11836  |

Simple Rule:
- 1 word ≈ 1-2 tokens
- "login" = 1 token
- "authentication" = 3 tokens (au + then + tication)

**Why Tokenization Matters for QA?**
- Every AI tool has a TOKEN LIMIT per request
- ChatGPT-4o: ~128,000 tokens
- Claude Sonnet: ~200,000 tokens
- If your requirement doc is too long → it gets CUT OFF
- Solution: Break large docs into smaller chunks

> Real QA Risk:
> You paste a 200-page BRD into ChatGPT.
> ChatGPT reads only ~96 pages. Rest gets cut off.
> You miss test cases for those features silently.
> Fix: Split document into 4 parts, send separately.

---

### Concept 2: Context Window

**What is it?**
Context Window = The MEMORY of an LLM
It is the maximum amount of text an LLM can
"see" and "remember" in a single conversation.

**Simple Analogy:**
Think of it like a whiteboard.
- The LLM can only read what is on the
  whiteboard RIGHT NOW.
- Anything outside the window = FORGOTTEN.

**Example:**
You share a 500-page requirement document.
- Claude (200k tokens) → Can read most of it ✅
- GPT-3.5 (4k tokens) → Can only read ~3 pages ❌

**Context Window Comparison:**
| Model            | Context Window   | Pages (approx) |
|------------------|------------------|----------------|
| GPT-4o           | 128,000 tokens   | ~96 pages      |
| Claude Sonnet    | 200,000 tokens   | ~150 pages     |
| Gemini 1.5 Pro   | 1,000,000 tokens | ~750 pages     |
| DeepSeek         | 64,000 tokens    | ~48 pages      |

**QA Use Case:**
- Reviewing a large BRD → Use Claude or Gemini
- Short prompt for one test case → Any model works

> Real QA Problem:
> You explain banking app in message 1.
> By message 20, GPT has forgotten message 1.
> It writes generic test cases, not app-specific.
> Fix: Use Claude for long sessions OR remind the AI
> at every message what you are testing.

---

### Concept 3: Reasoning

**What is it?**
Reasoning = The ability of the model to think
step-by-step and give logical, accurate answers.

**Two Types of Reasoning:**

**1. Basic Reasoning (All LLMs)**
- Simple Q&A
- Example: "What is boundary value analysis?"
- LLM directly gives the answer

**2. Chain-of-Thought Reasoning (Advanced)**
- LLM thinks step by step before answering
- Triggered by prompts like:
  "Think step by step..."
  "Review section by section..."

**Example — Without Reasoning Prompt:**
Prompt: "Is this test case correct?"
Output: "Yes, it looks fine." ← vague, useless

**Example — With Reasoning Prompt:**
Prompt: "Review this test case step by step
and identify any missing scenarios."
Output:
  Step 1: Preconditions → Missing ❌
  Step 2: Input data → Looks good ✅
  Step 3: Expected result → Too vague ❌
  Step 4: Missing edge cases → session expired?
  Step 5: Missing negative tests → SQL injection?

**QA Tip — Best Prompts for Reasoning:**
| Instead of this...       | Say this...                          |
|--------------------------|--------------------------------------|
| "Write test cases"       | "Think step by step and write..."   |
| "Is this bug valid?"     | "Analyze this bug report carefully" |
| "Review my test plan"    | "Review section by section and..."  |

---

## 4. Day 1 Summary

| Topic           | Key Takeaway                                  |
|-----------------|-----------------------------------------------|
| Tools           | ChatGPT, Claude, Gemini, n8n, Langflow, IDEs  |
| Generative AI   | Creates NEW content (text, code, images)      |
| LLM             | Large Language Model = AI brain               |
| Tokenization    | Text → Tokens → Numbers → AI processes it    |
| Context Window  | LLM memory — Claude has the largest (200k)    |
| Reasoning       | Step-by-step thinking = better QA output      |

---

## 5. Practice Tasks

- [x] Open ChatGPT → "Write test cases for login page step by step"
- [x] Open Claude → paste 2-page requirement → generate test cases
- [x] Compare both outputs and note differences
- [x] Try weak prompt vs strong reasoning prompt
