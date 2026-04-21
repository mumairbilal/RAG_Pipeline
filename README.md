# Enterprise RAG Architecture (Core Engine)

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Zephyr--7B-yellow.svg)
![ChromaDB](https://img.shields.io/badge/Vector_DB-ChromaDB-orange.svg)
![Status](https://img.shields.io/badge/Status-Deployed-success.svg)

## Project Overview
A modular, open-source **Retrieval-Augmented Generation (RAG)** pipeline designed for secure, context-aware information retrieval. Unlike standard API-wrapper applications, this project demonstrates a fully functional, local-first RAG architecture using state-of-the-art open-source Large Language Models (LLMs) and Vector Databases.

This system is built to eliminate LLM hallucinations by grounding generation strictly in provided knowledge bases, ensuring high accuracy for enterprise-level document intelligence.

## Technical Stack
* **LLM Engine:** `HuggingFaceH4/zephyr-7b-beta` (Optimized Instruct Model)
* **Embedding Model:** `sentence-transformers/all-MiniLM-L6-v2`
* **Vector Database:** `ChromaDB` (In-memory / Persistent semantic search)
* **Framework:** Custom Python logic (Modular approach without heavy LangChain abstractions for deeper control)

## ⚙️ Core Architecture Flow
1. **Data Ingestion:** Documents are loaded and processed.
2. **Vectorization:** Text is converted into high-dimensional numerical vectors using `all-MiniLM-L6-v2`.
3. **Semantic Storage:** Vectors are indexed into **ChromaDB** using Cosine Similarity metrics.
4. **Retrieval:** User queries are embedded, and the Top-K most relevant document chunks are retrieved via semantic search.
5. **Augmented Generation:** The context is dynamically injected into a strict system prompt and fed to **Zephyr-7B** to generate a highly accurate, grounded response.

## Key Engineering Highlights
* **Zero-API Dependency:** Uses Hugging Face inference and local vector storage, demonstrating cost-effective and privacy-focused AI deployment.
* **Strict Prompt Engineering:** Temperature is set to `0.2` to prioritize factual extraction over creative hallucination.
* **Cosine Similarity Search:** Implemented mathematically sound distance metrics for pinpoint document retrieval.

## Quick Start
To run this pipeline locally:

```bash
# Clone the repository
git clone [https://github.com/your-username/Enterprise-RAG-Core.git](https://github.com/your-username/Enterprise-RAG-Core.git)

# Install dependencies
pip install torch transformers sentence-transformers chromadb

# Run the core engine notebook
jupyter notebook RAG_Core_Engine.ipynb
