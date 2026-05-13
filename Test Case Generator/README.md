# 🤖 AI Test Case Generator Agent (ReAct + LangChain + OpenAI)

An intelligent AI-powered agent that automatically generates **high-quality software test cases** from plain English requirements using a **ReAct (Reason + Act)** workflow.

---

## 🚀 Overview

This project builds a QA automation assistant that:

* Understands software requirements
* Breaks them into structured components
* Generates detailed test cases
* Improves coverage with edge, negative, and security scenarios

All of this is done using:

* 🧠 OpenAI (GPT models)
* 🔗 LangChain Agents
* ⚙️ ReAct reasoning framework

---

## 🧩 Architecture

```
User Requirement
      ↓
AI Agent (ReAct)
      ↓
[Tool 1] Requirement Analyzer
      ↓
[Tool 2] Test Case Generator
      ↓
[Tool 3] Coverage Reviewer
      ↓
Final Test Cases (Markdown Table)
```

---

## 🛠️ Tech Stack

* Python
* LangChain
* OpenAI (GPT-4.1 / GPT-4.1-mini)
* Google Colab (recommended)

---
## 🚀 Project Demo

### 👉 Run the project here: Open in Google Colab
https://colab.research.google.com/drive/1HoGUAJPWYdoRlEKThSwVaBWAj1tr_oKM#scrollTo=xyI9VOgAtgCj
#### Simply open the notebook and run all cells — no local setup required.


## 🔑 Setup API Key

```python
import os
from getpass import getpass

os.environ["OPENAI_API_KEY"] = getpass("Enter your OpenAI API key: ")
```

---

## ⚙️ How It Works

The agent follows a **ReAct workflow**:

1. **Analyze Requirement**
2. **Generate Test Cases**
3. **Improve Coverage**

Each step is handled by a dedicated tool.

---

## 🧠 Tools

### 1. Requirement Analyzer

Extracts:

* Actors
* Flows
* Preconditions
* Edge cases
* Validation rules

### 2. Test Case Generator

Generates structured test cases:

| Field           | Description       |
| --------------- | ----------------- |
| TC ID           | Unique identifier |
| Scenario        | Test objective    |
| Steps           | Execution steps   |
| Test Data       | Input values      |
| Expected Result | Output validation |
| Priority        | High/Medium/Low   |

### 3. Coverage Reviewer

Enhances test coverage by adding:

* Negative scenarios
* Boundary cases
* Security cases
* Regression cases

---

## ▶️ Usage

### Step 1: Define Requirement

```python
requirement = """
User should be able to reset password using registered email.
System sends OTP valid for 10 minutes.
User can request OTP only 3 times in 30 minutes.
Password must meet complexity rules.
"""
```

---

### Step 2: Run Agent

```python
response = agent.invoke({
    "messages": [
        {"role": "user", "content": f"Generate test cases for:\n{requirement}"}
    ]
})

print(response["messages"][-1].content)
```

---

## 📊 Sample Output

```markdown
| TC ID | Scenario | Steps | Expected Result | Priority |
|------|----------|------|----------------|----------|
| TC_01 | Valid OTP | Enter correct OTP | Password reset success | High |
| TC_02 | Invalid OTP | Enter wrong OTP | Error message | High |
```

---

## 📁 Export Output

```python
with open("test_cases.md", "w") as f:
    f.write(response["messages"][-1].content)
```
---
