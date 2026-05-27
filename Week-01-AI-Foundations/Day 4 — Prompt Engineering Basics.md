# Day 1 - Prompt Engineering Basics
📅 Date: 27 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. What is Prompt Engineering?

A PROMPT is the text you type to an AI model.
Prompt Engineering is the skill of writing
prompts in the RIGHT WAY to get the BEST output.

Simple Definition:
Prompt Engineering = Learning how to talk
to AI so it gives you exactly what you need.

### Analogy:
Think of AI like a very smart new employee.
If you say: "Do the testing thing"
→ They are confused. Output is generic.

If you say: "You are a senior QA engineer.
Review this login test case step by step.
Check preconditions, steps, expected results,
and list all missing edge cases."
→ They know exactly what to do. Output is perfect.

Same AI. Different prompt. Completely different result.

---

## 2. Why QA Testers Need Prompt Engineering

Without Prompt Engineering:
- AI gives vague, generic test cases
- Output misses important edge cases
- You spend more time editing than saving
- AI does not understand your project context

With Prompt Engineering:
- AI gives detailed, specific test cases
- Output covers positive, negative, edge cases
- You save 70-80% of manual writing time
- AI understands your role, project, and context

### Real QA Comparison:

Weak Prompt:
"Write test cases for login"

Output:
TC01 - Enter username and password → Login success
TC02 - Enter wrong password → Error shown
(Only 2 generic test cases — useless)

Strong Prompt:
"You are a senior QA engineer testing a
banking application. Write detailed test cases
for the login feature. Include:
- Positive test cases
- Negative test cases
- Boundary value cases
- Security test cases
Format each test case with: ID, Title,
Precondition, Steps, Expected Result."

Output:
20+ detailed test cases covering all scenarios
including SQL injection, session timeout,
account lockout, password complexity rules.

Same AI. Same topic. 10x better output.

---

## 3. Steps for Effective Prompt Engineering

### Step 1: Define Your ROLE
Tell the AI who it should act as.

Example:
"You are a senior QA automation engineer
with 10 years of experience in Selenium."

Why: AI adjusts its language, detail level,
and expertise to match the role you give it.

---

### Step 2: Give CONTEXT
Tell the AI about your project or situation.

Example:
"We are testing a mobile banking app.
The app has modules: Login, Transfer,
Account History, and Profile Settings."

Why: Without context, AI gives generic answers.
With context, AI gives project-specific answers.

---

### Step 3: Give a CLEAR TASK
Tell the AI exactly what you want it to do.

Example:
"Write 10 test cases for the Login module."

Not: "Help me with testing" (too vague)

---

### Step 4: Specify the FORMAT
Tell the AI how you want the output structured.

Example:
"Format each test case as:
- Test Case ID
- Test Title
- Precondition
- Test Steps
- Expected Result
- Priority (High/Medium/Low)"

Why: Without format, AI gives unstructured output
that is hard to use directly.

---

### Step 5: Give EXAMPLES (Optional but powerful)
Show AI one example of what you want.

Example:
"Here is an example of the format I need:
TC001 | Valid Login | User is on login page |
1. Enter valid email 2. Enter valid password
3. Click Login | User sees dashboard | High"

Why: AI matches your exact style and format.

---

### Full Example — All 5 Steps Combined:

ROLE: "You are a senior QA engineer."
CONTEXT: "We are testing a banking app login page."
TASK: "Write 10 detailed test cases."
FORMAT: "Use columns: ID, Title, Steps, Expected Result."
EXAMPLE: "TC001 | Valid Login | 1. Enter email..."

Result: Professional test cases ready to use
in your test management tool directly.

---

## 4. Role-Based Prompting for QA

Role-based prompting means telling the AI
what ROLE to play before giving your task.

### Why It Works:
AI trained on millions of documents knows
how a "senior QA engineer" writes differently
from how a "junior developer" writes.
Giving a role activates the right knowledge.

### QA Roles You Can Use:

| Role Prompt                              | Best For                        |
|------------------------------------------|---------------------------------|
| "You are a senior QA engineer"           | General test case writing       |
| "You are a QA automation engineer"       | Writing Selenium/Playwright code|
| "You are a security tester"              | Security and penetration tests  |
| "You are a performance tester"           | Load and stress test scenarios  |
| "You are a mobile QA engineer"           | iOS and Android test cases      |
| "You are a QA lead reviewing a plan"     | Test plan review and feedback   |
| "You are a business analyst and QA"      | Requirement gap analysis        |

### Real QA Example:

Without Role:
Prompt: "Write security test cases for login"
Output: Basic test cases — wrong password, lockout.

With Role:
Prompt: "You are a security tester specializing
in OWASP testing methodology.
Write security test cases for a login page."

Output:
- SQL Injection in email field
- XSS attack in password field
- Brute force attack simulation
- Session fixation test
- CSRF token validation
- Password sent in plain text check
- SSL certificate validation

Much more detailed and professional output.

---

## 5. Zero Shot vs Precise Prompting

### Zero Shot Prompting

What is it?
You give the task directly with NO examples.
You "shoot" without showing the AI any sample.

When to use:
- Simple, straightforward tasks
- When you need a quick answer
- When format does not matter much

Example:
"Write test cases for a forgot password feature."

Output: Decent but generic. May miss edge cases.

---

### Precise Prompting (Few Shot)

What is it?
You give the task WITH examples, context,
format, and specific instructions.

When to use:
- Complex tasks with specific output needed
- When you need a specific format
- When working on a real project

Example:
"You are a senior QA engineer testing
a banking application.

Write test cases for the forgot password feature.
Include positive, negative, and security tests.

Use this exact format:
| TC ID | Title | Precondition | Steps | Expected Result | Priority |

Example of one test case:
| TC001 | Valid email reset | User has account |
1. Click forgot password
2. Enter registered email
3. Click send | Reset email received in inbox | High |

Now write 10 test cases following this format."

Output: Professional, structured, ready to use.

---

### Zero Shot vs Precise — Side by Side:

| Factor          | Zero Shot           | Precise Prompting      |
|-----------------|---------------------|------------------------|
| Time to write   | 10 seconds          | 2-3 minutes            |
| Output quality  | Generic             | Professional           |
| Format          | Random              | Exactly as specified   |
| Edge cases      | Often missed        | Covered thoroughly     |
| Best for        | Quick ideas         | Real project work      |
| QA use          | Brainstorming       | Actual test cases      |

> Key Point:
> Use Zero Shot for brainstorming and exploration.
> Use Precise Prompting for real QA deliverables.

---

## 6. Day 1 Summary

| Topic                  | Key Takeaway                                     |
|------------------------|--------------------------------------------------|
| Prompt Engineering     | Skill of writing prompts to get best AI output   |
| Why QA needs it        | Better prompts = better test cases, saves hours  |
| 5 Steps                | Role, Context, Task, Format, Example             |
| Role-based Prompting   | Tell AI what role to play for expert output      |
| Zero Shot              | Quick prompt, no example, generic output         |
| Precise Prompting      | Detailed prompt with format, professional output |

---

## 7. Practice Tasks

- [x] Write a Zero Shot prompt for any QA task
- [x] Write the same task as a Precise Prompt
- [x] Compare both outputs side by side
- [x] Try 3 different role prompts and compare
- [x] Push Day 1 notes to GitHub