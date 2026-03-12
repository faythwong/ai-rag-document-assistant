# AI-Powered RAG Document Assistant

An AI-powered Retrieval-Augmented Generation (RAG) system that automatically processes documents, stores embeddings in a vector database, and enables conversational search over enterprise knowledge.

This project demonstrates a production-ready AI automation pipeline built using:

- n8n (AI workflow orchestration)
- OpenAI embeddings
- Google Gemini LLM
- Supabase Vector Database
- LangChain nodes

The system automatically processes documents, converts them into embeddings, stores them in a vector database, and allows users to query their documents through a conversational AI interface.

---

## Key Features

- Automated document ingestion from Google Drive  
- PDF and CSV text extraction  
- AI-generated metadata using Gemini  
- Intelligent document chunking  
- Vector embeddings generation with OpenAI  
- Supabase vector database storage  
- Semantic document search  
- Conversational AI chatbot interface  

---

## System Architecture

### Document Processing Pipeline

Google Drive Upload  
↓  
File Detection Trigger  
↓  
Document Download  
↓  
Text Extraction  
↓  
AI Metadata Generation  
↓  
Document Chunking  
↓  
Embeddings Generation  
↓  
Supabase Vector Database  

---

### Chat Query Pipeline

User Question  
↓  
Query Embedding  
↓  
Vector Similarity Search  
↓  
Relevant Document Chunks  
↓  
LLM Response Generation  

---

## Tech Stack

| Layer | Technology |
|------|-------------|
| Workflow Orchestration | n8n |
| LLM | OpenAI GPT |
| AI Metadata Processing | Google Gemini |
| Vector Database | Supabase |
| Embeddings | OpenAI |
| AI Orchestration | LangChain nodes |

---

## Setup Instructions

### 1 Install n8n

```bash
npm install n8n -g

```

Alternatively, run n8n using Docker.

---

### 2. Import the Workflow

Open **n8n** and import the workflow file located in:

```
workflow/rag-document-assistant-workflow.json
```

---

### 3. Configure API Credentials

Inside n8n, configure the following credentials:

- Google Drive API
- OpenAI API
- Google Gemini API
- Supabase API

Ensure each service has the necessary API keys and permissions.

---

### 4. Create the Vector Database Table

Run the following SQL inside your Supabase project:

```sql
CREATE TABLE public.documents (
  id bigserial PRIMARY KEY,
  content text,
  metadata jsonb,
  embedding vector
);
```

This table will store document chunks and their vector embeddings for semantic search.

---

### 5. Configure Google Drive Trigger

Update the **Google Drive Trigger node** to monitor the folder where documents will be uploaded.

Supported file types:

- PDF
- CSV
- Google Docs

---

### 6. Run the Workflow

Upload a document into the monitored Google Drive folder.

The workflow will automatically:

1. Detect the new file
2. Download and extract text
3. Generate metadata
4. Split the document into chunks
5. Generate embeddings
6. Store vectors in Supabase

Your documents will now be searchable through the AI chatbot.

## Documentation

- [System Architecture](docs/architecture.md)
- [Example Queries](docs/example-queries.md)
- [Demo Scenario](demo/demo-scenario.md)
