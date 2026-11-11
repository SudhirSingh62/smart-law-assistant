# ⚖️ Smart Law Assistant

A Retrieval-Augmented Generation (RAG) chatbot that helps lawyers and legal professionals analyze legal documents (service agreements, contracts, NDAs) by answering questions based on an uploaded PDF.

**Author:** Sudhir Singh  
**Contact:** work.sudhir15@gmail.com  
**License:** MIT

## Features

- Upload and process legal PDF documents
- Ask detailed questions about the document
- Text embeddings via the Gemini API (`gemini-embedding-001`), so no local torch model and a small deploy footprint
- Streaming answers from Google Gemini (3.8 Flash or Flash Latest)
- Chat interface with history, model/temperature/retrieval settings and page-numbered source passages
- Shows the context chunks used for each answer
- Built with LangChain, Streamlit and FAISS

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Streamlit |
| LLM | Google Gemini 3.8 Flash / Flash Latest |
| Embeddings | Gemini Embedding 001 |
| Vector Store | FAISS (in-memory) |
| Orchestration | LangChain |
| PDF Parsing | PyPDF |

## Setup

1. Clone the repo
   ```bash
   git clone https://github.com/SudhirSingh62/smart-law-assistant.git
   cd smart-law-assistant
   ```
2. Create a virtual environment
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```
3. Create a `.env` file with your Gemini key (get one at https://aistudio.google.com/apikey)
   ```
   GOOGLE_API_KEY=your-gemini-api-key
   ```
4. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```
5. Run the app
   ```bash
   streamlit run app.py
   ```

## Deploying on Streamlit Community Cloud

Push the repo to GitHub, create a new app pointing at `app.py`, and add `GOOGLE_API_KEY` under Settings → Secrets.

## Docker Deployment

```bash
docker build -t smart-law-assistant .
docker run -p 8501:8501 --env-file .env smart-law-assistant
```

## Disclaimer

This tool is an aid for legal professionals and does not provide legal advice. Verify all output against the source document.

---

© 2026 Sudhir Singh. All rights reserved.
