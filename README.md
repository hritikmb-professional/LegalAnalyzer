# Legal Contract Analyzer

AI-powered contract analysis system with RAG (Retrieval-Augmented Generation) for risk assessment and intelligent Q&A on legal documents.

## Features

**Automated Contract Analysis**
- Risk assessment and balance scoring (0-100)
- Key clause extraction and analysis
- Issue identification in plain language
- Overall contract assessment

**RAG-based Q&A**
- Ask specific questions about uploaded contracts
- Context-aware responses with explanations
- Retrieves relevant contract sections automatically
- Answers grounded in actual contract text

**Document Support**
- PDF and DOCX file formats
- Text extraction and chunking
- Persistent vector storage for re-querying

## Tech Stack

**Backend (Flask)**
- **LLM:** Google Gemini 2.0 Flash
- **Embeddings:** SentenceTransformer (all-MiniLM-L6-v2)
- **Vector DB:** ChromaDB (persistent storage)
- **Document Processing:** PyPDF2, python-docx

**Frontend**
- Tailwind CSS with dark theme
- Interactive file upload interface
- Real-time analysis display
- Q&A chat interface

## Architecture

```
Upload Contract → Extract Text → Generate Analysis (Gemini)
                              ↓
                        Chunk Text → Embed → Store (ChromaDB)
                              ↓
                        Ask Questions → Retrieve Context → Answer (Gemini)
```

## Setup

```bash
# Backend
cd back
pip install flask flask-cors sentence-transformers chromadb google-generativeai PyPDF2 python-docx

# Configure API key in app.py
GEMINI_API_KEY = "your_key_here"

# Run server
python app.py
```

```bash
# Frontend
cd front
# Open contract_analyzer.html in browser
```

## API Endpoints

**POST /upload_document**
- Upload PDF/DOCX contract
- Returns: analysis + chunks indexed

**POST /ask_question**
- Query uploaded contract
- Returns: answer + explanation from contract text

## Use Cases

- Pre-signing contract review
- Risk identification for non-lawyers
- Quick clause lookup
- Legal document Q&A

Analysis explains technical terms in plain language, making legal documents accessible to everyone.
