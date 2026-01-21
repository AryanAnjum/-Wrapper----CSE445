RAG (Retrieval-Augmented Generation) System
A production-ready Retrieval-Augmented Generation (RAG) system with multi-format document support, speech input/output, and dual LLM support (local + remote fallback).

This project was developed as a CSE445 course project, satisfying the requirement for:

Local Knowledge Base + RAG Pipeline + Local LLM + Remote LLM Fallback

📋 Table of Contents
 • Overview
 • Features
 • System Requirements
 • Installation Guide
    • Windows Setup
    • macOS Setup
 • Getting Started
 • Usage
 • Project Structure
 • Configuration
 • Working with Git
 • Development Workflow
 • Troubleshooting
 • Contributing Guidelines

📌 Overview
 • This project implements a Retrieval-Augmented Generation (RAG) system that:
 • Loads and processes documents from multiple formats
 • Converts documents into semantic embeddings using FAISS
 • Retrieves relevant context for user queries
 • Generates accurate answers using LLMs
 • Supports speech-to-text and text-to-speech
 • Automatically switches between local and remote LLMs
 • The system is designed to be modular, extensible, and production-ready.

 ✨ Features
📄 Document Processing
 • Supports PDF, DOCX, PPTX, XLSX, CSV, TXT, HTML, Markdown, JSON
 • Image OCR support
 • Recursive chunking with configurable size and overlap
 • Metadata tracking for source attribution

🔍 Vector Search
 • FAISS vector database
 • 384-dimensional embeddings
 • SentenceTransformer (all-MiniLM-L6-v2)
 • Persistent local index storage

🤖 LLM Integration
 • Groq API (remote LLM fallback)
 • Ollama (local LLM for offline usage)
 • Automatic fallback mechanism
 • Configurable models

 🔧 System Requirements
Minimum
 • Python: 3.13.2+
 • RAM: 4 GB (8 GB recommended)
 • Storage: ~2 GB
 • Internet: Required for initial setup and Groq API
Optional (Local LLM)
 • Ollama
 • Additional 4–8 GB storage

🎤 Speech Capabilities
Speech-to-Text: OpenAI Whisper
Text-to-Speech: pyttsx3
Cross-platform support
🖥 Interactive Interface
Menu-driven CLI
Text and voice query modes
Real-time progress and status output

📥 Installation Guide
Clone Repository
In bash
git clone https://github.com/rkrakib11/RAG.git
cd RAG

🪟 Windows Setup
Install uv
Download from: https://github.com/astral-sh/uv/releases

Verify:
In bash
uv --version

Install Dependencies:
In bash
uv sync
.\.venv\Scripts\activate

Environment Variables:
Create .env:

In bash
GROQ_API_KEY=your_groq_api_key
OPENAI_API_KEY=your_openai_api_key  # optional

Run
In bash
python main.py

🍎 macOS Setup
Install uv
brew install uv

Install Dependencies
uv sync
source .venv/bin/activate

Optional: Local LLM
brew install ollama
ollama pull mistral
ollama serve

Run
python main.py

🚀 Getting Started
python main.py


Commands:
 • t → Text query
 • s → Speech query
 • rebuild → Rebuild FAISS index
 • exit → Quit

📖 Usage:
Text Query Example:
Enter your question: What is machine learning?

Speech Query:
 • Speak after beep
 • System transcribes, retrieves context, answers, and speaks back

📁 Project Structure:
WRAPPER---CSE445/
├── __pycache__/
│   ├── app.cpython-313.pyc
│   └── asr.cpython-313.pyc
│
├── src/
│   ├── __pycache__/
│   │   ├── __init__.cpython-313.pyc
│   │   ├── data_loader.cpython-313.pyc
│   │   ├── document_rag.cpython-313.pyc
│   │   ├── embedding.cpython-313.pyc
│   │   ├── local_llm.cpython-313.pyc
│   │   ├── search.cpython-313.pyc
│   │   ├── transcript_rag.cpython-313.pyc
│   │   └── vectorstore.cpython-313.pyc
│   │
│   ├── __init__.py
│   ├── data_loader.py        # Load and preprocess documents
│   ├── document_rag.py       # RAG pipeline for document-based queries
│   ├── embedding.py          # Text chunking and embedding generation
│   ├── local_llm.py          # Local LLM (Ollama) integration
│   ├── search.py             # Semantic search logic
│   ├── transcript_rag.py     # Speech-based RAG handling
│   └── vectorstore.py        # FAISS vector store management
│
├── app.py                    # Application-level logic
├── asr.py                    # Speech-to-text (Whisper) handling
├── main.py                   # Entry point (interactive CLI)
├── LICENSE
├── pyproject.toml            # Project configuration
├── requirements.txt          # Python dependencies
└── uv.lock                   # Locked dependency versions

👥 Contributing Guidelines
 • Follow PEP-8
 • Use meaningful commit messages
 • Never commit .env
 • Test before pushing
 
🎓 Academic Information
 • Course: CSE445
 • Project Type: Final Project
 • Topic: Retrieval-Augmented Generation (RAG) And Local LLM And OpenAi

📌 Status
 • Python Version: 3.13.2+
 • Build: Stable
 • Deployment: Local
 • Last Updated: December 2025


 
