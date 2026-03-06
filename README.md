# RAG-Powered Multi-Format Q&A System
A Streamlit-based RAG app that lets users upload PDFs, DOCX, TXT files or web URLs and ask questions. Uses HuggingFace embeddings, FAISS vector search, and Meta LLaMA 3 8B to retrieve relevant context and generate accurate answers — demonstrating end-to-end GenAI pipeline development.


## Overview
A Retrieval-Augmented Generation (RAG) application that enables 
users to query their own documents using semantic search and 
LLM-powered answers. Supports PDF, DOCX, TXT, plain text, 
and web URLs.

---

## Tech Stack
- **Frontend:** Streamlit
- **LLM:** Meta LLaMA 3 8B (HuggingFace Inference API)
- **Embeddings:** sentence-transformers/all-mpnet-base-v2
- **Vector Store:** FAISS
- **Framework:** LangChain
- **Language:** Python 3.10+

---

## Features
- Multi-format document ingestion (PDF, DOCX, TXT, URL, Text)
- Semantic chunking and embedding pipeline
- FAISS-based vector similarity search
- Context-aware Q&A via LLaMA 3 8B
- Simple, no-code Streamlit UI

---

## Architecture
Input → Chunk → Embed → FAISS Index → Retrieve → LLM → Answer

---

## Setup

### 1. Clone the Repository
git clone <repo>
cd rag-qa-app

### 2. Install Dependencies
pip install -r requirements.txt

### 3. Configure API Key
Create a file named secret_api_keys.py:
huggingface_api_key = "your_huggingface_token_here"

### 4. Run the App
streamlit run app.py

---

## Requirements
streamlit
faiss-cpu
langchain
langchain-community
langchain-huggingface
sentence-transformers
PyPDF2
python-docx
numpy

---

## How It Works
1. User selects input type and uploads content
2. Content is split into 1000-character chunks (100 overlap)
3. Chunks are embedded using HuggingFace sentence-transformers
4. Embeddings stored in FAISS vector index
5. User query retrieves top relevant chunks
6. LLaMA 3 8B generates answer using retrieved context

---

## Known Limitations
- HuggingFace free tier has rate limits and latency
- No answer source citation currently
- Single document session (no persistence)

---

## Future Improvements
- Add OpenAI / Groq as LLM alternatives
- Display source chunks with answers
- Multi-document support
- Deploy on Streamlit Cloud
- Add conversation memory (multi-turn Q&A)

---
