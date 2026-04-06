# Grounded RAG PDF Question Answering

Retrieval-Augmented Generation (RAG) system for answering questions from PDF documents while minimizing hallucinations and allowing supported logical inference.

## 🚀 Overview

This project implements an end-to-end RAG pipeline that:
- Extracts text from PDF documents
- Splits content into overlapping chunks
- Embeds chunks using a sentence transformer
- Retrieves relevant context using FAISS similarity search
- Generates grounded answers using a large language model with carefully designed prompts

The system is designed to **prevent hallucinated facts** (e.g., invented locations) while still allowing **reasonable inference** (e.g., scholarships imply financial aid).

---

## 🧠 Key Features

- PDF text extraction using **PyPDF2**
- Semantic chunking with overlap
- Vector search using **FAISS**
- Dense embeddings via **Sentence Transformers**
- Answer generation with **Mistral-Nemo-Instruct**
- Prompt design focused on **faithfulness and grounded reasoning**

---

## 🏗️ Pipeline Architecture

**PDF** → Text Extraction → Chunking → Embeddings → FAISS Index  
**User Question** → Top-k Relevant Chunks → Grounded LLM Prompt → **Final Answer**

---

## 🛠️ Tech Stack

- Python
- PyPDF2
- Sentence-Transformers
- FAISS
- Hugging Face Transformers
- Mistral-Nemo-Instruct LLM

---

## 🔍 Prompting Strategy

The prompt enforces:

- Use of only retrieved document text
- Logical inference only when directly supported
- No addition of unstated specific facts
- Safe fallback when information is not mentioned
- This balances accuracy and usability in real-world RAG systems.

---

