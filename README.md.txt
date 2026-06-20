# RAG Chatbot Project

RAGChat is a simple Python-based RAG project that answers questions from PDF documents. I built this project to search information from my own PDF books and research papers using embeddings and a vector database.

The system reads PDFs, extracts text, breaks the text into smaller chunks, creates embeddings, stores them in FAISS, and retrieves the most relevant content when a user asks a question.

## Project Pipeline

```text
PDFs → Text Extraction → Chunking → Embeddings → FAISS Vector Store → Search Results with Sources
```

## Features

* Reads multiple PDF files from a folder
* Extracts text using PyMuPDF
* Splits long text into smaller chunks
* Creates embeddings using Sentence Transformers
* Stores embeddings in FAISS vector database
* Searches the most relevant chunks for a user question
* Shows PDF filename, page number, score, and retrieved text

## Tech Stack

* Python
* Jupyter Notebook
* PyMuPDF
* SentenceTransformers
* FAISS
* NumPy
* tqdm
* Pickle

## Folder Structure

```text
RAGChat_Project/
│
├── RAGChat.ipynb
├── README.md
├── pdfs/
└── vector_store/
```

`pdfs/` contains the PDF files.
`vector_store/` stores the FAISS index and metadata after running the notebook.

## How to Run

First, install the required libraries:

```bash
pip install pymupdf sentence-transformers faiss-cpu numpy tqdm
```

Then place your PDF files inside the `pdfs` folder.

Open the notebook:

```text
RAGChaT.ipynb
```

Run the cells in order.

In the final cell, change the question as needed:

```python
question = "What is computational neuroscience?"
```

The output will show the most relevant PDF content along with the source filename and page number.

## Sample Questions

* What is computational neuroscience?
* Explain neural coding.
* What is the Hodgkin-Huxley model?
* What are computational models of neurons?
* What is systems biology?

## Current Status

This is a working retrieval-based RAG prototype. It can extract text from PDFs, create embeddings, store them in FAISS, and retrieve relevant chunks for a user query.

## Limitations

* It works best with text-based PDFs.
* Scanned PDFs may need OCR support.
* The current version retrieves relevant chunks but does not yet generate a polished LLM-based answer.
* Large PDFs may take more time during the first embedding step.

## Future Improvements

* Add OCR for scanned PDFs
* Add a Streamlit chat interface
* Add local LLM answer generation using Ollama
* Add latency measurement
* Add retrieval evaluation metrics

