# Day 3 - QA-Specific Frameworks & RICE POT
📅 Date: 29 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. What is RICE POT?

RICE POT is a QA-specific prompt framework
designed specifically for software testers.

It gives AI all the information it needs
to generate complete, professional QA output.

RICE POT stands for:

R — Role        (who the AI should be)
I — Input       (what requirement or feature)
C — Context     (project background)
E — Expectation (what you expect as output)

P — Persona     (end user of the application)
O — Output      (format and structure needed)
T — Tone        (professional/technical/simple)

---

## 2. RICE POT — Each Part Explained

### R — Role
Tell AI what QA role to play.

Examples:
- "You are a senior QA engineer"
- "You are a QA automation engineer"
- "You are a security tester"
- "You are a mobile QA engineer"
- "You are a QA lead reviewing a test plan"

Why it matters:
AI gives expert-level output matching the role.
A security tester role gives security test cases.
An automation role gives code-ready output.

---

### I — Input
The requirement, feature, or content you
want the AI to work with.

Examples:
- Paste the actual requirement text
- Describe the feature in detail
- Share the user story
- Paste the API documentation

Why it matters:
The more specific your input, the more
specific and accurate the AI output.

---

### C — Context
Background information about your project.

Examples:
- Type of application (web, mobile, API)
- Technology stack being used
- Target users of the application
- Any known constraints or limitations

Why it matters:
Without context AI gives generic output.
With context AI gives project-specific output.

---

### E — Expectation
What you want the AI to deliver.

Examples:
- "Write 15 test cases"
- "Find all missing scenarios"
- "Write automation code for this"
- "Review this test plan and give feedback"

Why it matters:
Clear expectation = clear output.
Vague expectation = vague output.

---

### P — Persona
Who is the end user of the application.

Examples:
- "The end user is a doctor accessing patient records"
- "The user is a non-technical bank customer"
- "The user is an admin managing the dashboard"
- "The user is a teenager using a social media app"

Why it matters:
AI considers the user perspective when
generating test cases. A non-technical user
needs different test scenarios than an admin.

---

### O — Output
Exact format and structure of the output.

Examples:
- Table with specific columns
- Numbered list
- Code in a specific language
- Bug report in a specific template

Why it matters:
Output format directly affects how much
editing you need to do after AI response.
Correct format = zero editing needed.

---

### T — Tone
The writing style of the output.

Examples:
- Professional (for client deliverables)
- Technical (for developer communication)
- Simple (for non-technical stakeholders)
- Formal (for audit documentation)

Why it matters:
Test cases for clients need professional tone.
Code review comments need technical tone.
Status reports need simple, clear tone.

---

## 3. RICE POT Template

```
Role: You are a [QA role].

Input: Here is the feature/requirement:
[paste requirement or describe feature]

Context: We are testing a [app type].
Tech stack: [frontend, backend, database].
The application is used by [target users].

Expectation: Your task is to [specific task].
Include [what to cover — positive, negative, security].

Persona: The end user is [user description].
Consider their technical level and usage patterns.

Output: Format the output as:
[exact format — table columns, template, code structure]

Tone: Write in a [professional/technical/simple] tone.
```

---

## 4. RICE POT — Real QA Examples

### Example 1: Login Feature Test Cases

Role:
You are a senior QA engineer with expertise
in web application security testing.

Input:
Feature: User Login
Requirements:
- User enters email and password to login
- Show error for invalid credentials
- Lock account after 3 failed attempts
- Session expires after 30 minutes of inactivity
- Password must be minimum 8 characters

Context:
We are testing a mobile banking web application.
Tech stack: React frontend, Node.js backend,
PostgreSQL database.
The app is used by retail bank customers.

Expectation:
Write 15 test cases covering:
- Positive scenarios (happy path)
- Negative scenarios (invalid inputs)
- Boundary value cases
- Security test cases
- Session management cases

Persona:
The end user is a retail bank customer.
They are non-technical, aged 25-60.
They access the app on both mobile and desktop.

Output:
Format as a table:
| TC ID | Title | Precondition | Test Steps | Expected Result | Priority | Test Type |

Tone: Professional. Suitable for client delivery.

---

Expected Output (sample):
| TC001 | Valid login | User registered | Enter valid email + password, click Login | Dashboard visible | High | Positive |
| TC002 | Wrong password | User registered | Enter valid email + wrong password, click Login | Error: Invalid credentials | High | Negative |
| TC003 | Account lockout | User registered | Enter wrong password 3 times | Account locked message shown | High | Negative |
| TC004 | Empty email | Login page open | Leave email blank, click Login | Validation: Email required | Medium | Negative |
| TC005 | SQL injection | Login page open | Enter ' OR 1=1-- in email field | Login rejected, no DB error | High | Security |
...and 10 more

---

### Example 2: API Test Cases

Role:
You are a QA automation engineer specializing
in REST API testing using Postman and Newman.

Input:
API Endpoint: POST /api/v1/login
Request Body: { "email": "string", "password": "string" }
Success Response: 200 { "token": "jwt_token", "user": {} }
Error Responses: 400 Bad Request, 401 Unauthorized,
429 Too Many Requests, 500 Internal Server Error

Context:
We are testing the authentication API for
an e-commerce mobile application.
Backend is built in Java Spring Boot.

Expectation:
Write API test cases covering all response
codes and edge cases including rate limiting
and token validation.

Persona:
This API is consumed by mobile app developers.
The token must be secure and expire in 24 hours.

Output:
| TC ID | Scenario | Method | Request Body | Expected Status | Expected Response |

Tone: Technical. For developer and QA team use.

---

### Example 3: Automation Script

Role:
You are a QA automation engineer with
5 years of Playwright and TypeScript experience.

Input:
Write automation tests for login page at:
URL: https://demo.testapp.com/login
Acceptance Criteria:
- Valid login redirects to /dashboard
- Invalid password shows "Invalid credentials"
- Empty fields show validation messages
- Account locks after 3 failed attempts

Context:
We use Playwright with TypeScript.
Page Object Model pattern is followed.
Tests run in CI/CD pipeline on GitHub Actions.

Expectation:
Write a complete test file with:
- describe block for login tests
- beforeEach to navigate to login page
- Separate test for each scenario
- Proper assertions with meaningful messages

Persona:
Tests will be maintained by junior QA engineers.
Code must be readable and well commented.

Output:
Complete TypeScript Playwright test file.
Follow POM pattern. Include import statements.

Tone: Technical. Clean, readable code with comments.

---

## 5. When to Use Which Framework

| Situation                               | Best Framework |
|-----------------------------------------|----------------|
| Writing test cases quickly              | STAR           |
| Need specific number of test cases      | CLEAR          |
| Writing automation code                 | CRISP          |
| Complete QA deliverable for client      | RICE POT       |
| Reviewing test plan or bug report       | Chain-of-Thought|
| Quick brainstorm of test scenarios      | Zero Shot      |
| Real project with full context needed   | RICE POT       |

---

## 6. RICE POT vs Other Frameworks

| Factor            | STAR     | CLEAR    | CRISP    | RICE POT    |
|-------------------|----------|----------|----------|-------------|
| QA Specific       | No       | No       | No       | Yes ✅      |
| Covers User Persona| No      | No       | No       | Yes ✅      |
| Controls Tone     | No       | No       | No       | Yes ✅      |
| Best for QA work  | Partial  | Partial  | Partial  | Fully ✅    |
| Complexity        | Simple   | Simple   | Medium   | Detailed    |
| Output Quality    | Good     | Good     | Good     | Best        |

---

## 7. Your Personal RICE POT Template (.md file)

Save this as: rice-pot-template.md

```markdown
# RICE POT Prompt Template
## Project: [Your Project Name]

---

**Role:**
You are a [senior QA engineer / automation engineer /
security tester / QA lead].

**Input:**
[Paste requirement, user story, or feature description here]

**Context:**
Application: [web / mobile / API / desktop]
Tech Stack: [frontend / backend / database / automation tool]
Domain: [e-commerce / banking / healthcare / etc]
Team: [your team size and structure]

**Expectation:**
Task: [Write test cases / Review / Generate code / Analyze]
Coverage: [positive / negative / boundary / security / performance]
Count: [number of test cases or outputs needed]

**Persona:**
End User: [who uses this application]
Technical Level: [technical / non-technical]
Device: [mobile / desktop / both]

**Output:**
Format: [table / list / code / report]
Columns (if table): [TC ID | Title | Steps | Expected | Priority]
Language (if code): [Python / TypeScript / Java]

**Tone:**
[Professional / Technical / Simple / Formal]
```

---

## 8. Week 2 Summary

| Day   | Topic                        | Key Takeaway                                  |
|-------|------------------------------|-----------------------------------------------|
| Day 1 | What is Prompt Engineering   | Skill of talking to AI to get best output     |
| Day 1 | 5 Steps                      | Role, Context, Task, Format, Example          |
| Day 1 | Role-based Prompting         | Tell AI its role = expert level output        |
| Day 1 | Zero Shot vs Precise         | Zero Shot = quick, Precise = professional     |
| Day 2 | QA-Style Prompts             | Role + Context + Task + Format                |
| Day 2 | Chain-of-Thought             | Step by step = thorough QA analysis           |
| Day 2 | STAR / CLEAR / CRISP         | Structured frameworks for consistent output   |
| Day 2 | Context Templates            | .md file saves time across all AI sessions    |
| Day 3 | RICE POT                     | Best QA-specific framework for all QA tasks   |
| Day 3 | When to use which framework  | RICE POT for full deliverables, CoT for review|

---

## 9. Practice Tasks

- [ ] Write a RICE POT prompt for a feature you know
- [ ] Compare RICE POT output vs Zero Shot output
- [ ] Create your own rice-pot-template.md
- [ ] Create your own project-context.md
- [ ] Use RICE POT to generate test cases for
      a login, signup, or payment feature
- [ ] Push all Week 2 notes to GitHub
- [ ] Update README — mark Week 2 as Complete ✅

---

> Week 1 Complete!
