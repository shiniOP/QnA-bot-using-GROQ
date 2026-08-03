# Research Paper Q&A Chatbot using LangChain, Groq, FAISS, and Ollama Embeddings

This project is a Retrieval-Augmented Generation (RAG) based Research Paper Question Answering chatbot built with **Streamlit** and **LangChain**. It enables users to ask natural language questions about a collection of research papers in PDF format and receive accurate, context-aware answers.

The application loads research papers from a local directory, splits them into manageable text chunks using **RecursiveCharacterTextSplitter**, and converts them into vector embeddings using **Ollama's Qwen3 Embedding model**. These embeddings are stored in a **FAISS Vector Database** for efficient semantic similarity search.

When a user submits a query, the system retrieves the most relevant document chunks from the FAISS vector store and passes them, along with a custom prompt, to the **Groq LLM (GPT-OSS-120B)**. The model generates responses strictly based on the retrieved context, reducing hallucinations and improving answer accuracy.

## Features

* Upload and process research papers stored in a local directory.
* Automatic PDF loading using `PyPDFDirectoryLoader`.
* Recursive text chunking for efficient retrieval.
* Semantic embeddings using **Qwen3 Embedding (Ollama)**.
* Fast similarity search with **FAISS**.
* Context-aware question answering using **Groq GPT-OSS-120B**.
* Interactive web interface built with **Streamlit**.
* Expandable section to display the retrieved document chunks used for generating the answer.
* Session-based vector database creation to avoid repeated processing.

## Tech Stack

* Python
* Streamlit
* LangChain
* LangChain Classic
* Groq API
* Ollama (Qwen3 Embedding)
* FAISS
* PyPDF
* RecursiveCharacterTextSplitter
* Python Dotenv

## Workflow

1. Load research papers from the local directory.
2. Split documents into overlapping text chunks.
3. Generate embeddings using Qwen3 Embedding through Ollama.
4. Store embeddings in a FAISS vector database.
5. Retrieve the most relevant document chunks for a user's query.
6. Send the retrieved context and user question to the Groq LLM.
7. Display the generated answer along with the retrieved supporting document chunks.
