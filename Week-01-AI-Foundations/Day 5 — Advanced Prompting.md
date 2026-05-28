# Day 2 - Advanced Prompting
📅 Date: 28 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. Writing Your First QA-Style Prompt

A QA-style prompt has 4 key ingredients:
1. Role — who the AI should be
2. Context — what you are testing
3. Task — what you want
4. Format — how you want the output

### Template:
"You are a [ROLE].
We are testing [CONTEXT].
Your task is to [TASK].
Format the output as [FORMAT]."

---

### Your First QA Prompt — Login Feature:

"You are a senior QA engineer with expertise
in web application testing.

We are testing the login page of an e-commerce
website. The page has email field, password
field, login button, and forgot password link.

Your task is to write 10 detailed test cases
covering positive, negative, boundary value,
and security scenarios.

Format each test case as:
| TC ID | Title | Precondition | Steps | Expected Result | Priority |"

---

### Your First QA Prompt — API Testing:

"You are a QA automation engineer specializing
in REST API testing.

We have a POST /api/login endpoint that accepts
email and password in JSON body and returns
a JWT token on success.

Your task is to write test cases for this
API endpoint covering all status codes:
200, 400, 401, 403, 500.

Format:
| TC ID | Scenario | Request Body | Expected Status | Expected Response |"

---

### Your First QA Prompt — Bug Report:

"You are a senior QA engineer.

I found this bug: The login button on the
mobile app does nothing when tapped on
iPhone 14 running iOS 17 in Safari browser.
It works fine on Chrome mobile.

Your task is to write a professional bug report.

Format:
- Title
- Environment
- Severity and Priority
- Steps to Reproduce
- Expected Result
- Actual Result
- Possible Root Cause"

---

## 2. Chain-of-Thought Prompting

### What is it?
Chain-of-Thought (CoT) = You ask the AI to
THINK STEP BY STEP before giving the answer.

This forces the AI to reason through the
problem logically instead of guessing.

### Why it works for QA:
QA requires systematic thinking.
Asking AI to think step by step gives
you much more thorough and accurate output.

### How to trigger Chain-of-Thought:
Add these phrases to your prompt:
- "Think step by step"
- "Reason through this carefully"
- "Analyze this section by section"
- "Walk through each scenario one by one"

---

### CoT Example 1 — Test Case Review:

Without CoT:
Prompt: "Is this test case good?"
Output: "Yes it looks fine." (useless)

With CoT:
Prompt: "Review this test case step by step.
For each section check:
Step 1: Are preconditions complete?
Step 2: Are test steps clear and atomic?
Step 3: Is expected result measurable?
Step 4: Are edge cases covered?
Step 5: Are negative scenarios included?
List issues found in each step."

Output:
Step 1: Preconditions — Missing browser version ❌
Step 2: Test steps — Step 3 is ambiguous ❌
Step 3: Expected result — Too vague, not measurable ❌
Step 4: Edge cases — Missing session timeout ❌
Step 5: Negative tests — SQL injection not covered ❌

Professional, actionable review.

---

### CoT Example 2 — Requirement Analysis:

Prompt:
"You are a QA engineer.
Analyze this requirement step by step:
'User should be able to reset password
using registered email address.'

Step 1: Identify all happy path scenarios
Step 2: Identify all negative scenarios
Step 3: Identify all edge cases
Step 4: Identify security concerns
Step 5: List any missing or ambiguous requirements"

Output: Complete analysis covering all angles.
Ready to use for test planning directly.

---

### CoT Example 3 — Bug Analysis:

Prompt:
"You are a senior QA engineer.
Analyze this bug step by step:
'Payment fails for orders above $1000'

Step 1: What could be the possible root causes?
Step 2: What test cases would reproduce this?
Step 3: What boundary values should be tested?
Step 4: What regression tests are needed?
Step 5: What is the severity and business impact?"

---

## 3. Prompt Frameworks

Prompt frameworks are structured templates
that ensure you never miss important parts
of a prompt.

---

### Framework 1: STAR

S — Situation  (what is the context)
T — Task       (what needs to be done)
A — Action     (how should AI approach it)
R — Result     (what format should the output be)

### STAR Template:
"Situation: [describe the context]
Task: [what you need]
Action: [how AI should approach it]
Result: [format and type of output needed]"

### STAR QA Example:

Situation: We are testing a food delivery app.
The checkout page allows users to apply
promo codes before placing an order.

Task: Write test cases for the promo code
feature.

Action: Think step by step. Cover positive tests,
negative tests, boundary values, and
integration with payment module.

Result: Format as a table with columns:
TC ID, Scenario, Input Data, Expected Result, Priority.

---

Output from STAR prompt:
TC001 | Valid promo code | SAVE20 | 20% discount applied | High
TC002 | Expired promo code | EXPIRED10 | Error: code expired | High
TC003 | Invalid code | ABCXYZ | Error: invalid code | High
TC004 | Empty promo field | (blank) | Order proceeds normally | Medium
TC005 | Promo applied twice | SAVE20 twice | Error: already applied | High
TC006 | Case sensitivity | save20 vs SAVE20 | Both should work | Medium
...and more

---

### Framework 2: CLEAR

C — Context    (background information)
L — Length     (how long the output should be)
E — Expertise  (what level of expert AI should be)
A — Action     (what you want AI to do)
R — Result     (desired output format)

### CLEAR Template:
"Context: [background]
Length: [short/detailed/number of items]
Expertise: [junior/senior/expert level]
Action: [specific task]
Result: [output format]"

### CLEAR QA Example:

Context: We are testing a login page for
a healthcare web application. The app is
used by doctors to access patient records.

Length: Write exactly 15 test cases.

Expertise: Act as a senior QA engineer
with healthcare domain experience.

Action: Write test cases covering functional,
security, and compliance (HIPAA) scenarios.

Result: Format as a table with TC ID, Title,
Steps, Expected Result, and Test Type columns.

---

### Framework 3: CRISP

C — Context    (project background)
R — Role       (who AI should be)
I — Input      (what data or info you are providing)
S — Specifics  (detailed instructions)
P — Purpose    (why you need this / end goal)

### CRISP Template:
"Context: [project context]
Role: [AI persona]
Input: [data or requirement you are sharing]
Specifics: [detailed instructions]
Purpose: [end goal of the output]"

### CRISP QA Example:

Context: We are building an automation
framework for an e-commerce website using
Playwright and TypeScript.

Role: You are a QA automation engineer
with 8 years of Playwright experience.

Input: Here is the login page URL and
the acceptance criteria:
- User can login with valid credentials
- User sees error for invalid password
- Account locks after 5 failed attempts

Specifics: Write a complete Playwright test
file with describe block, beforeEach hook,
and separate it() for each scenario.
Include proper assertions and error messages.

Purpose: This code will be added directly
to our test suite and run in CI/CD pipeline.

---

### Framework Comparison:

| Framework | Best For                        | Key Strength          |
|-----------|---------------------------------|-----------------------|
| STAR      | Test case writing                | Clear structure       |
| CLEAR     | When output length matters       | Controls detail level |
| CRISP     | Automation code generation       | Technical precision   |

---

## 4. Context Creation via Templates (.md files)

### What is Context Creation?
Instead of explaining your project every time
you open a new AI chat, you create a
CONTEXT FILE (.md) that you paste at the
start of every conversation.

This saves time and ensures consistent,
project-specific output every time.

### Why .md files?
- Clean, readable format
- Works perfectly in VS Code and GitHub
- Easy to paste into any AI tool
- Can be version controlled with your project

---

### QA Context Template — project-context.md:

```
# Project Context for AI Prompts

## Project Name: [Your Project Name]

## Application Type: [Web / Mobile / API / Desktop]

## Tech Stack:
- Frontend: [React / Angular / Vue]
- Backend: [Node.js / Java / Python]
- Database: [MySQL / PostgreSQL / MongoDB]
- Automation: [Selenium / Playwright / Cypress]

## Test Management Tool: [Jira / TestRail / Zephyr]

## My Role: [QA Engineer / QA Lead / Automation Engineer]

## Current Module Being Tested: [Login / Payment / etc]

## Key Requirements:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

## Output Format Preference:
- Test cases as table: ID | Title | Steps | Expected Result
- Bug reports with: Title | Severity | Steps | Expected | Actual
- Code in: [Language and Framework]
```

---

### How to Use Context Template:

Step 1: Create project-context.md in VS Code
Step 2: Fill in your project details once
Step 3: At start of every AI chat, paste it:
  "Here is my project context:
   [paste your .md content]
   Now help me with: [your task]"
Step 4: AI now knows your full project.
        No need to explain again.

---

### Real QA Example — With and Without Context:

Without Context File:
Day 1: You explain banking app to AI (5 minutes)
Day 2: You open new chat. Explain again (5 minutes)
Day 3: New chat. Explain again (5 minutes)
Week total: 25 minutes wasted explaining.
Output: Slightly different each time.

With Context File:
Day 1: Paste context.md → task (30 seconds)
Day 2: Paste context.md → task (30 seconds)
Day 3: Paste context.md → task (30 seconds)
Week total: 2.5 minutes.
Output: Consistent every time.

---

## 5. Day 2 Summary

| Topic               | Key Takeaway                                       |
|---------------------|----------------------------------------------------|
| QA-Style Prompt     | Role + Context + Task + Format = perfect output    |
| Chain-of-Thought    | "Step by step" forces AI to think like a QA tester |
| STAR Framework      | Best for test case writing tasks                   |
| CLEAR Framework     | Best when output length and detail level matters   |
| CRISP Framework     | Best for automation code generation                |
| Context Templates   | .md file saves project context for reuse           |

---

## 6. Practice Tasks

- [ ] Write your first QA-style prompt for any feature
- [ ] Try Chain-of-Thought on a test case review
- [ ] Write one prompt using STAR framework
- [ ] Write one prompt using CRISP framework
- [ ] Create your own project-context.md file
- [ ] Push Day 2 notes to GitHub