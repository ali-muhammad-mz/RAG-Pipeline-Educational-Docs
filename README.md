# RAG-Pipeline-Educational-Docs

A Retrieval-Augmented Generation (RAG) pipeline that lets you query your own PDF documents using semantic search and a Groq LLM.

---

## How it works

```
PDFs → Chunks → Embeddings → ChromaDB → Query → Groq LLM → Answer
```

---

## Stack

| Component | Tool |
|---|---|
| Document Chunking | LangChain `RecursiveCharacterTextSplitter` |
| Embeddings | `all-MiniLM-L6-v2` (SentenceTransformers) |
| Vector Store | ChromaDB |
| LLM | Groq (`openai/gpt-oss-20b`) |

---

## Setup

1. **Clone the repo**
```bash
git clone <repo-url>
cd project
```

2. **Install dependencies**
```bash
pip install -r package-requirements.txt
```

3. **Add your Groq API key**

Create a `.env` file inside the `notebook/` folder:
```
GROQ_API_KEY=your_api_key_here
```

---

## Usage

Open and run `notebook/project.ipynb` step by step:

1. Load and chunk PDFs
2. Generate embeddings
3. Store in ChromaDB
4. Query using natural language

```python
retriever = Retriever(collection=collection)
answer = retriever.ask("What are the construction phases in project management?")
print(answer)
```

---

## Project Structure

```
project/
├── notebook/
│   ├── .env
│   └── project.ipynb
├── data/
│   └── pdfs/
├── main.py
├── package-requirements.txt
└── README.md
```
