# 🧠 ReAct News Agent

A lightweight Python project that implements a **ReAct-style (Reason + Act) autonomous agent** to fetch, process, and summarize the latest news articles using real-time data from Google News RSS.

---

## 🚀 Features

* 🔍 **Search latest news** using Google News RSS
* 🌐 **Fetch full article content** from web pages
* 🧹 **Clean and extract readable text** using Trafilatura + BeautifulSoup fallback
* 🧠 **Autonomous reasoning loop (ReAct pattern)**
* ✂️ **Extractive summarization** using word frequency scoring
* 🗂️ **Step-by-step memory tracking** for transparency

---

## 🧩 How It Works

The agent follows a **ReAct loop**:

1. **Think** → Decide next action
2. **Act** → Perform action (search, fetch, summarize)
3. **Observe** → Store results
4. Repeat until final answer

### Agent Flow

```
User Query → Search News → Fetch Article → Summarize → Final Output
```

---
## 🚀 Project Demo

### 👉 Run the project here: Open in Google Colab
https://colab.research.google.com/drive/1_0rUun0UFuutFQEw7R2b19dRepzsDmG5#scrollTo=LAJmuZeZKfrV

#### Simply open the notebook and run all cells — no local setup required.
## 📦 Installation

```bash
pip install requests feedparser trafilatura beautifulsoup4
```

---

## 🛠️ Usage

```python
agent = ReActNewsAgent()
result = agent.run("latest news on artificial intelligence")

print(result)
```

---

## 📄 Example Output

```json
{
  "title": "AI breakthrough in healthcare",
  "url": "https://example.com/article",
  "summary": "Researchers have developed...",
  "memory": [...]
}
```

---

## 🧠 Core Components

### 1. ReActNewsAgent

* Controls the reasoning loop
* Maintains internal memory
* Decides actions dynamically

### 2. Tools

* `search_news()` → Fetch RSS results
* `fetch_web_content()` → Extract article text
* `summarize_text()` → Generate summary

### 3. Memory System

Stores:

* Thoughts
* Actions
* Observations

This makes the agent **interpretable and debuggable**.

---
