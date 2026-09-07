# 🤖 LangGraph RAG & Agentic Assistant Demo

A full-stack agentic RAG application built with **LangGraph**, **LangChain**, **Streamlit**, **FAISS**, **Google Gemini Embeddings**, and **Groq LLM**.

This application combines deterministic tool calling (arithmetic tools) with document retrieval (RAG) over a custom knowledge base, featuring a live interactive Streamlit UI with real-time tool execution traces.

---

## 🌟 Key Features

- **🧠 LangGraph State Agent**: Graph-based flow for intelligent tool selection, state management, and multi-turn conversation.
- **📚 Retrieval-Augmented Generation (RAG)**: Document search powered by Google's `gemini-embedding-001` embeddings and local `FAISS` vector store.
- **⚡ Fast Inference with Groq**: Powered by `ChatGroq` (`openai/gpt-oss-20b`) for rapid tool calling and response generation.
- **💻 Streamlit Web UI**: Elegant chat interface with a live sidebar displaying detailed **Tool Traces** (tool inputs, arguments, and outputs per query).
- **🛠️ Built-in Tools**:
  - `search_docs`: Searches vector index for AI/ML, LangGraph, RAG, and Transformer concepts.
  - `add`, `multiply`, `divide`: Standard mathematical utilities for arithmetic queries.

---

## 📁 Repository Structure

```
.
├── agent.py            # LangGraph agent definitions & tool configurations
├── app.py              # Streamlit Web Application UI
├── ingest.py           # Script to chunk documents & generate FAISS vector index
├── sample_docs/        # Raw text files for knowledge base ingestion
│   └── ai_concepts.txt
├── src/                # Project source package
├── experiment.ipynb    # Prototyping & testing notebook
├── pyproject.toml      # Project metadata & dependencies (uv compatible)
├── uv.lock             # Lockfile for reproducible environment setup
└── .gitignore          # Git exclusion rules
```

---

## 🚀 Quickstart Guide

### Prerequisites

- Python 3.13+
- [uv](https://github.com/astral-sh/uv) (recommended) or `pip`

### 1. Environment Setup

Clone the repository and install dependencies:

```bash
git clone https://github.com/Aryanuser07/rag-demo.git
cd rag-demo
uv sync
```

### 2. Configure Environment Variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key_here
GOOGLE_API_KEY=your_google_gemini_api_key_here
```

### 3. Ingest Documents into Vector Store

Run the ingestion script to build the FAISS index from `sample_docs/`:

```bash
uv run python ingest.py
```

### 4. Run the Streamlit Application

Start the interactive web app:

```bash
uv run streamlit run app.py
```

Open your browser at `http://localhost:8501`.

---

## 🛠️ Built With

- [LangGraph](https://github.com/langchain-ai/langgraph)
- [LangChain](https://github.com/langchain-ai/langchain)
- [Streamlit](https://streamlit.io/)
- [FAISS](https://github.com/facebookresearch/faiss)
- [Google Gemini API](https://ai.google.dev/)
- [Groq AI](https://groq.com/)
