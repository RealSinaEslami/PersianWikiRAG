# PersianWikiRAG

A Retrieval-Augmented Generation (RAG) system for Persian Wikipedia built using Qdrant, Sentence Transformers, and Qwen3-14B.

The project creates a searchable Persian knowledge base from Wikipedia articles and provides context-aware answers through a Large Language Model (LLM).

---

## Features

- Persian Wikipedia preprocessing and cleaning
- Text normalization and chunking
- Embedding generation using Sentence Transformers
- Vector storage with Qdrant
- Semantic search using Cosine Similarity
- Retrieval-Augmented Generation (RAG)
- Response generation using Qwen3-14B
- Fully local deployment support

---

## Project Architecture

```text
Wikipedia Dataset
        │
        ▼
Data Preprocess
        │
        ▼
Vectorize
(Embedding Generation)
        │
        ▼
Qdrant Vector Database
        │
        ▼
Retrieval
(Cosine Similarity Search)
        │
        ▼
RAG Pipeline
        │
        ▼
Qwen3-14B
        │
        ▼
Generated Answer

________________________________

PersianWikiRAG/
│
├── Data Preprocess/
│   └── data_preprocess.ipynb
│
├── Vectorize/
│   └── vectorize_data.ipynb
│
├── Retrieval/
│   └── retrieval.ipynb
│
├── RAG/
│   └── rag.ipynb
│
├── LLM/
│   └── llm.ipynb
│
├── requirements.txt
│
└── README.md
```

Technologies
Python
Qdrant
Sentence Transformers
Transformers
PyTorch
Qwen3-14B
FastAPI (optional)
Docker (optional)
Workflow
1. Data Preprocessing

Wikipedia articles are cleaned, normalized, and divided into smaller chunks suitable for embedding generation.

2. Vectorization

Each chunk is converted into a dense vector representation using a sentence embedding model.

3. Vector Database

Embeddings and metadata are stored inside Qdrant.

4. Retrieval

User queries are embedded and compared against stored vectors using cosine similarity.

5. Augmented Generation

Retrieved contexts are injected into the prompt and passed to Qwen3-14B to generate a grounded answer.

Example

User Query:
برج میلاد در چه سالی ساخته شد؟

Assistant:
برج میلاد در **سال ۱۳۸۷** (که به تقویم میلادی معادل سال ۲۰۰۷ است) ساخته و با شعار «آسمان نزدیک است» گشایش یافت. این مراسم در **روز ۱۶ مهر ۱۳۸۷** برگزار شد.
