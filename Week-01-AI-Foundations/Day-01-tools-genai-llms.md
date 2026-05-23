# Day 1 - Tools Overview, Generative AI & LLMs
📅 Date: 23 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. Tools Overview

### AI Tools:
**ChatGPT (by OpenAI)**
- A conversational AI that can generate text, 
  write code, and answer questions
- QA Use: Writing test cases, generating bug 
  reports, creating automation code

**Claude (by Anthropic)**
- An AI assistant best known for analyzing 
  long documents and giving detailed explanations
- QA Use: Reviewing test plans, analyzing 
  large requirement documents
- Special: Has the largest context window 
  among all AI tools

**Gemini (by Google)**
- Google's AI assistant integrated with 
  Google Workspace
- QA Use: Works well with Google Docs, 
  Sheets, and Drive for QA documentation

### Automation Tools:
**n8n**
- A workflow automation tool that connects 
  different apps and automates repetitive tasks
- QA Use: Automatically create test cases 
  when a Jira ticket is raised
- Example Flow: 
  Jira Ticket Created → AI generates test cases 
  → Test cases saved in Google Sheets

**Langflow**
- A visual tool to build AI-powered workflows 
  without writing much code
- QA Use: Build AI agents that understand 
  requirements and generate test strategies

### IDEs (Code Editors):
**VS Code**
- Most popular free code editor
- Used for: Writing notes, automation scripts, 
  and managing project files

**Cursor**
- VS Code with built-in AI assistance
- Helps write and fix code using AI suggestions

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
| Tool        | What it Generates |
|-------------|-------------------|
| ChatGPT     | Text, Code        |
| Claude      | Text, Analysis    |
| Midjourney  | Images            |
| GitHub Copilot | Code           |
| Sora        | Videos            |

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
### Concept 1: Tokenization (continued)

**Example:**
Input Text: "Write test case for login"

How LLM breaks it into tokens:
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

---

### Concept 2: Context Window

**What is it?**
Context Window = The MEMORY of an LLM
It is the maximum amount of text an LLM can 
"see" and "remember" in a single conversation.

**Simple Analogy:**
Think of it like a whiteboard.
- The LLM can only read what is written on 
  the whiteboard RIGHT NOW.
- Anything erased (outside the window) = FORGOTTEN.

**Example:**
You share a 500-page requirement document.
- Claude (200k tokens) → Can read most of it ✅
- GPT-3.5 (4k tokens) → Can only read ~3 pages ❌

**Context Window Comparison:**
| Model           | Context Window | Pages (approx) |
|-----------------|----------------|----------------|
| GPT-4o          | 128,000 tokens | ~96 pages      |
| Claude Sonnet   | 200,000 tokens | ~150 pages     |
| Gemini 1.5 Pro  | 1,000,000 tokens | ~750 pages   |
| DeepSeek        | 64,000 tokens  | ~48 pages      |

**QA Use Case:**
- Reviewing a large BRD (Business Requirement Doc)
  → Use Claude or Gemini for best results
- Short prompt for one test case
  → Any model works fine

---

### Concept 3: Reasoning

**What is it?**
Reasoning = LLM ki sochne ki taakat
The ability of the model to think step-by-step 
and give logical, accurate answers.

**Two Types of Reasoning:**

**1. Basic Reasoning (All LLMs)**
- Simple Q&A
- Example: "What is boundary value analysis?"
- LLM directly gives the answer

**2. Chain-of-Thought Reasoning (Advanced)**
- LLM thinks step by step before answering
- Triggered by prompts like:
  "Think step by step..."
  "Let's reason through this..."

**Example — Without Reasoning Prompt:**
Prompt: "Is this test case correct?"
Output: "Yes, it looks fine." ← vague answer

**Example — With Reasoning Prompt:**
Prompt: "Review this test case step by step 
and identify any missing scenarios."
Output:
Step 1: Checking preconditions → Missing ❌
Step 2: Checking input data → Looks good ✅  
Step 3: Checking expected result → Vague ❌
Step 4: Recommendation → Add negative test cases

**QA Tip — Best Prompts for Reasoning:**
| Instead of this...         | Say this...                          |
|----------------------------|--------------------------------------|
| "Write test cases"         | "Think step by step and write..."   |
| "Is this bug valid?"       | "Analyze this bug report carefully" |
| "Review my test plan"      | "Review section by section and..."  |

---

## 4. Day 1 Summary

| Topic             | Key Takeaway                                  |
|-------------------|-----------------------------------------------|
| Tools             | ChatGPT, Claude, Gemini, n8n, Langflow, IDEs  |
| Generative AI     | Creates NEW content (text, code, images)      |
| LLM               | Large Language Model = AI brain               |
| Tokenization      | Text → Tokens → Numbers → AI processes it    |
| Context Window    | LLM ki memory — Claude has the largest        |
| Reasoning         | Step-by-step thinking = better QA output      |

---

