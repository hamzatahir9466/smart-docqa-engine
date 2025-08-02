#  Smart DocQA Engine

An intelligent document Question Answering (QA) API built with FastAPI, OpenAI GPT-4, vector search (FAISS/Chroma), and LangChain. This project enables you to upload documents (PDF/Markdown/Text), ask questions, and receive accurate, context-aware answers using Retrieval-Augmented Generation (RAG).

---

##  Features

| Feature            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
|  Document Upload | Upload PDFs, Markdown, or text files                                        |
|  Chunking        | Split documents into semantically meaningful segments                       |
|  Embedding       | Generate vector embeddings using OpenAI's `text-embedding-3-small` model     |
|  Vector Store    | Store and retrieve chunks using FAISS or Chroma                             |
|  RAG Pipeline    | Retrieve relevant chunks → Send to GPT-4 → Return concise answer            |
|  Token Counting  | Estimate LLM token usage for cost-aware prompting                          |
|  Testing         | Pytest-based test suite for ingestion and querying                          |
|  Docs            | Auto-generated FastAPI API docs + architecture overview                     |

---

## Architecture

```bash
Client → FastAPI Backend
           ├── PDF/Text Ingestion
           ├── Text Chunking
           ├── Embedding via OpenAI
           ├── Vector Store (FAISS/Chroma)
           ├── RAG Pipeline (LangChain)
           └── GPT-4 Answer Generation
```
## Tech Stack

- Backend: FastAPI, Pydantic
- LLM: OpenAI GPT-4 API
- Vector DB: FAISS or Chroma
- Embedding: OpenAI text-embedding-3-small
- Parsing: PyMuPDF, Markdown, UTF-8 decoders
- Utilities: LangChain, tiktoken, logging, dotenv
- Testing: Pytest, HTTPX
- Stretch: Docker, JWT auth, conversation memory

  ---
##  Quickstart (Local Setup)

1. Clone the repo
   
   ```bash
   git clone https://github.com/yourusername/smart-docqa-engine.git
   cd smart-docqa-engine
   ```
2. Create virtual environment
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Add your OpenAI API Key

    Create a .env file:

   ```bash
   OPENAI_API_KEY=your-openai-api-key

   ```
4. Run the app
  ```bash
  uvicorn app.main:app --reload
  ```
5. Access Swagger UI

   Open http://localhost:8000/docs

----
## Project Structure
```bash
smart-docqa-engine/
├── app/
│   ├── api/            # FastAPI routes
│   ├── services/       # Core logic (ingestion, embedding, RAG)
│   ├── utils/          # Helpers (chunking, token counting)
│   ├── core/           # Configs, logging
│   └── main.py         # FastAPI app entry
├── tests/              # Unit tests
├── requirements.txt    # Python dependencies
├── README.md
└── .env

```

## Road Map

- PDF/Text ingestion
-  Chunking with tiktoken
-  Embedding and vector storage
-  RAG pipeline with GPT-4
-  Token usage optimization
-  Answer logging and evaluation
-  Dockerization
-  React-based UI (optional)
-  User authentication (stretch goal)
-  Conversation memory


