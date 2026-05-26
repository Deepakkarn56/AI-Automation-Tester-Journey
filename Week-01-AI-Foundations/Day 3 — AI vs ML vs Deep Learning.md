# Day 3 - AI Concepts: AI vs ML vs Deep Learning
📅 Date: 26 May 2026
📚 Course: AI Automation Tester Blueprint

---

## 1. The AI Family Tree

Most people use AI, ML, and Deep Learning
as the same word. They are NOT the same.

AI is the biggest concept.
ML lives inside AI.
Deep Learning lives inside ML.
LLMs live inside Deep Learning.

AI
└── Machine Learning (ML)
    └── Deep Learning (DL)
        └── LLMs / Generative AI

---

## 2. Artificial Intelligence (AI)

### What is it?
Making machines smart enough to perform tasks
that normally require human intelligence —
thinking, deciding, solving problems.

### Real World Examples:
| Example                      | Type  |
|------------------------------|-------|
| Google Maps route finding    | AI    |
| Email spam filter            | AI    |
| Face unlock on phone         | AI    |
| Chess playing computer       | AI    |
| ChatGPT answering questions  | AI    |

> Real QA Example:
> Tool: Testim.io (AI-powered test automation)
>
> Problem: Traditional tests break when a button
> moves 5 pixels. Developer changes UI slightly →
> 100 tests fail overnight. Tester wastes full day fixing.
>
> With AI: The tool UNDERSTANDS what the button is,
> not just where it is on screen. Button moves →
> AI still finds and clicks it. Test never breaks.
> This is AI making smart decisions like a human.

---

## 3. Machine Learning (ML)

### What is it?
Teaching a machine to LEARN FROM DATA
without manually programming every rule.

### Old Way vs ML Way:

**Without ML:**
Developer writes every rule manually:
  IF "free money" in email → SPAM
  IF "win prize" in email → SPAM
Problem: Cannot write rules for everything.

**With ML:**
Give model 1 million labeled emails.
Model learns patterns automatically.
Detects new spam it has never seen before.
No manual rules needed.

### How ML Works:
Step 1: TRAINING → feed model data with answers
Step 2: TESTING → give new unseen data, check accuracy
Step 3: PREDICTION → model is ready for real world

### Types of ML:

**Supervised Learning:**
- Model learns from labeled data
- QA Use: Predict if a test will pass or fail

**Unsupervised Learning:**
- Model finds patterns in unlabeled data
- QA Use: Auto-group similar bug reports together

**Reinforcement Learning:**
- Model learns by trial and error
- QA Use: AI agent that explores app and finds bugs

> Real QA Example:
> Tool: Test Impact Analysis in CI/CD pipeline
>
> Problem: You have 5000 test cases.
> Running all of them takes 8 hours.
> Developer changes only the login module.
>
> Without ML: Run all 5000. Wait 8 hours every time.
>
> With ML: Model trained on past results predicts
> "only 150 tests are affected by this change."
> Run only 150 tests. Done in 30 minutes.
> Saves 7.5 hours per release.
> Nobody programmed this rule — ML learned it.

---

## 4. Deep Learning (DL)

### What is it?
A type of ML that uses NEURAL NETWORKS with
many layers to understand complex data like
images, audio, and text.

### Why "Deep"?
Because it uses MANY LAYERS of processing.
Each layer learns something more complex.

Layer 1 → Learns basic shapes (lines, edges)
Layer 2 → Learns patterns (eyes, nose)
Layer 3 → Learns full faces
Layer 4 → Identifies the person

The more layers = the deeper the network.

### Where Deep Learning is Used:
| Application         | Example                      |
|---------------------|------------------------------|
| Image Recognition   | Google Photos face tagging   |
| Voice Recognition   | Siri, Alexa, Google Assistant|
| Language Translation| Google Translate             |
| Text Generation     | ChatGPT, Claude, Gemini      |
| Object Detection    | Self-driving car cameras     |

> Real QA Example:
> Tool: Applitools Eyes (Visual AI Testing)
>
> Problem: App has 50 screens.
> After every release, manually checking all
> 50 screens takes 3-4 hours.
>
> With Deep Learning (Applitools):
> Tool takes screenshot of every screen →
> DL model compares to baseline →
> Detects wrong font, shifted button, broken
> layout, wrong color automatically.
> Flags only real differences.
> Ignores normal rendering variations.
>
> Result: 50 screens checked in 5 minutes
> instead of 4 hours.

---

## 5. Side-by-Side Comparison

| Factor          | AI                   | ML                    | Deep Learning          |
|-----------------|----------------------|-----------------------|------------------------|
| Definition      | Smart machines       | Learn from data       | Learn via neural nets  |
| Scope           | Broadest concept     | Subset of AI          | Subset of ML           |
| Data Needed     | Varies               | Moderate              | Very large datasets    |
| Human Rules     | Can use rules        | Learns rules from data| Learns features itself |
| Best For        | Any smart task       | Predictions, patterns | Images, text, audio    |
| QA Tool Example | Testim.io            | Test impact analysis  | Applitools Eyes        |

---

## 6. Full QA Pipeline — All Three Together

Code pushed by developer
  ↓
ML predicts which 150 of 5000 tests to run
  ↓
Selenium runs the 150 selected tests
  ↓
Deep Learning checks all UI screenshots
(Applitools visual regression)
  ↓
AI writes bug reports for all failures
(ChatGPT / Claude)
  ↓
n8n sends reports to Jira automatically
+ Slack notification to team

Result: Entire QA process runs automatically.
Tester only reviews results — no repetitive work.

---

## 7. Simple Memory Trick

AI            = The DREAM  (make machines smart)
ML            = The METHOD (learn from data)
Deep Learning = The ENGINE (deep neural networks)
LLM           = The TOOL   (ChatGPT, Claude daily use)

---

## 8. Day 3 Summary

| Topic          | Key Takeaway                                     |
|----------------|--------------------------------------------------|
| AI             | Broadest concept — making machines smart         |
| ML             | Machines learn patterns from data automatically  |
| Deep Learning  | Neural networks — powers images, text, audio     |
| LLMs           | Type of Deep Learning — ChatGPT, Claude, Gemini  |
| AI in QA       | Self-healing tests (Testim.io)                   |
| ML in QA       | Run only affected tests — saves hours in CI/CD   |
| DL in QA       | Visual regression across 50 screens in 5 minutes |

---

## 9. Practice Tasks

- [ ] Draw the AI family tree from memory
- [ ] Give 2 real QA examples for ML
- [ ] Give 2 real QA examples for Deep Learning
- [ ] Explain difference between ML and DL
      to someone in simple words
- [ ] Push Day 3 notes to GitHub
- [ ] Update README — mark Week 1 as Complete ✅

---

> Week 1 Complete!
> Next: Week 2 — Prompt Engineering for QA Testers