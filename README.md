# 🤖🧠 Agentic RAG

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-🚀-yellowgreen?logo=chainlink)](https://github.com/langchain-ai/langchain)
[![Ollama](https://img.shields.io/badge/Ollama-🦙-orange)](https://ollama.com/)
[![FAISS](https://img.shields.io/badge/FAISS-Vector_Search-9cf?logo=vectorworks)](https://github.com/facebookresearch/faiss)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Agentic RAG** is a modular, agent-based Retrieval-Augmented Generation (RAG) system for health and gym supplement information retrieval.  
> It leverages LangChain, LangGraph, Ollama, and FAISS to provide intelligent, context-aware answers from a vector database built from scientific PDFs.

---

## 🗂️ Features

- 🤖 **Agentic Workflow:** Modular nodes for agent, retriever, grader, rewriter, and generator.
- 🔍 **Vector Search:** Fast, semantic document retrieval using FAISS and Ollama embeddings.
- 📄 **PDF Knowledge Base:** Ingests and indexes scientific PDFs on health and gym supplements.
- 🧪 **Interactive Notebook:** Jupyter/VSCode notebook for experimentation and extension.
- 🛠️ **Customizable:** Easily add new documents, models, or tools.

---

## 📁 Folder Structure

```
Agentic RAG/
│
├── Agentic Rag.ipynb                # Main notebook: agent workflow, graph, and demo
├── Vector Stores and Retrievals.ipynb # Notebook for vector store creation and retrieval
├── download-1.png                   # System diagram
├── download.png                     # Additional image
│
├── health_supplements/
│   ├── index.faiss                  # FAISS vector index
│   ├── index.pkl                    # Pickled metadata/docstore
│
├── rag-dataset/
│   ├── README.md                    # Dataset info
│   ├── gym supplements/
│   │   ├── 1. Analysis of Actual Fitness Supplement.pdf
│   │   └── 2. High Prevalence of Supplement Intake.pdf
│   └── health supplements/
│       ├── 1. dietary supplements - for whom.pdf
│       ├── 2. Nutraceuticals research.pdf
│       └── 3.health_supplements_side_effects.pdf
│
├── requirements.txt                 # Python dependencies
├── .env                             # Environment variables (API keys, etc.)
├── start.ipynb                      # Quickstart notebook
├── text_to_sql.ipynb                # Example: text-to-SQL agent
├── tst.py                           # Misc/test script
```

---

## 🚀 Quickstart

1. **Clone the repository:**
   ```sh
   git clone https://github.com/yourusername/agentic-rag.git
   cd agentic-rag
   ```

2. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

3. **Set up environment:**
   - Copy `.env.example` to `.env` and add your API keys (e.g., for Ollama, Tavily, etc.).

4. **Run the main notebook:**
   - Open `Agentic Rag.ipynb` in VSCode or Jupyter.
   - Follow the cells to start the agentic RAG workflow.

5. **(Optional) Rebuild vector store:**
   - Use `Vector Stores and Retrievals.ipynb` to add new PDFs or re-index documents.

---

## 🧩 How It Works

- 🧬 **Embeddings:** Documents are embedded using Ollama's `nomic-embed-text:v1.5`.
- 🗂️ **Retrieval:** FAISS provides fast similarity search over the embedded documents.
- 🕸️ **Agentic Graph:** LangGraph orchestrates the flow: agent → retriever → grader → rewriter/generator.
- 🤖 **LLM:** Uses Ollama's Qwen2.5 or other local models for all reasoning and generation.

---

## 💡 Example Query

```python
from langchain_core.messages import HumanMessage

query = {"messages": [HumanMessage("what are the risks of taking too much protein?")]}
for output in graph.stream(query):
    print(output)
```

---

## 📊 System Graph

![System Graph](download-1.png)

---

## 📚 References

- [LangChain](https://github.com/langchain-ai/langchain)
- [LangGraph](https://github.com/langchain-ai/langgraph)
- [Ollama](https://ollama.com/)
- [FAISS](https://github.com/facebookresearch/faiss)

---

## 📝 License

MIT License

---

*Built with ❤️ for research and educational purposes.*
