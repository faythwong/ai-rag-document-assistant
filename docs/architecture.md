# System Architecture

This project implements a **Retrieval-Augmented Generation (RAG)** architecture that enables users to query documents using AI.

The system converts uploaded documents into vector embeddings and stores them in a vector database for semantic search.

---

## Document Processing Pipeline

1. **Google Drive Trigger**
   - Monitors a folder for newly uploaded documents.

2. **Document Download**
   - Automatically downloads uploaded files.

3. **Text Extraction**
   - Extracts text from supported formats:
     - PDF
     - CSV
     - Google Docs

4. **Metadata Generation**
   - AI generates document title and description using an LLM.

5. **Document Chunking**
   - Documents are split into smaller chunks for efficient vector storage.

6. **Embeddings Generation**
   - OpenAI embeddings convert text into vectors.

7. **Vector Storage**
   - Embeddings are stored in Supabase Vector Database.

---

## Query Pipeline

1. **User Query**
   - User asks a question through the chat interface.

2. **Query Embedding**
   - The question is converted into an embedding vector.

3. **Vector Search**
   - Supabase returns the most relevant document chunks.

4. **Context Retrieval**
   - Relevant chunks are sent to the language model.

5. **Answer Generation**
   - The AI generates an answer using retrieved context.

---

## RAG Benefits

This architecture enables:

- semantic search
- context-aware responses
- reduced hallucinations
- scalable document knowledge systems
