# 📄 Knowledge Assistant (RAG-based PDF Chatbot)

### A simple Retrieval-Augmented Generation (RAG) chatbot that allows users to upload documents and ask questions based on their content using OpenAI and FAISS.

## 🚀 Features
* Upload multiple documents (PDF, TXT, Markdown)
* Extract and process text automatically
* Split documents into chunks
* Generate embeddings using OpenAI
* Store embeddings in FAISS vector database
* Retrieve relevant context for queries
* Answer questions using LLM (gpt-4o-mini)
* Prevent hallucinations by restricting answers to context
## 🧠 Architecture
```
Upload Documents
      ↓
Load & Extract Text
      ↓
Chunk Text
      ↓
Generate Embeddings (OpenAI)
      ↓
Store in FAISS
      ↓
User Query
      ↓
Retrieve Relevant Chunks
      ↓
LLM (Context + Prompt)
      ↓
Final Answer
```
## 📦 Installation
``` pip install -U langchain langchain-community langchain-openai langchain-text-splitters faiss-cpu pypdf ```

## 🔑 Setup API Key

```
import os
from getpass import getpass

os.environ["OPENAI_API_KEY"] = getpass("Enter your OpenAI API key: ")

```
## 📂 Usage

### 1. Upload Documents
```
from google.colab import files
uploaded = files.upload()
```
### 2. Load Documents

Supports:

* .pdf
* .txt
* .md
3. Split into Chunks
```
from langchain_text_splitters import RecursiveCharacterTextSplitter

text_splitter = RecursiveCharacterTextSplitter(
    chunk_size=500,
    chunk_overlap=100
)

docs = text_splitter.split_documents(documents)

```
### 4. Generate Embeddings
```
from langchain_openai import OpenAIEmbeddings

embeddings = OpenAIEmbeddings(model="text-embedding-3-small")
```
### 5. Store in FAISS
```   
from langchain_community.vectorstores import FAISS

vector_db = FAISS.from_documents(docs, embeddings)
```
### 6. Ask Questions

```
query = "Summarize the main topic of the document."
print(ask_question(query))
```

## Google Colab Notebook
https://colab.research.google.com/drive/1rB8Hxy_TNESxYZTty0QPmIIrAHjHNAhC#scrollTo=WdakbNAsWDQV


## 💬 Prompt Template
```
You are a helpful assistant.

Answer the question based ONLY on the context below.

If the answer is not in the context, say: "I don't know."
```
