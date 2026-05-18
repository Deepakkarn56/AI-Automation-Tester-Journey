# Day 1 - Tools Overview, Generative AI & LLMs
📅 Date: 16 May 2026
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