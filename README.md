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

or run using Docker.

### 2. Import the Workflow

Import the workflow file:

workflow/rag-document-assistant-workflow.json

into your n8n instance.

### 3. Configure Credentials

Add credentials inside n8n for:

- Google Drive API
- OpenAI API
- Google Gemini API
- Supabase API

### 4. Create Vector Database Table

Run this SQL inside Supabase:

CREATE TABLE public.documents (
  id bigserial PRIMARY KEY,
  content text,
  metadata jsonb,
  embedding vector
);
