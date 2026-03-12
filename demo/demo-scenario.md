# Demo Scenario

This example demonstrates how the RAG document assistant processes documents and answers questions.

---

## Step 1 — Upload Document

Upload a document into the monitored Google Drive folder.

Example files:

- financial report PDF
- company handbook
- CSV dataset
- business contract

---

## Step 2 — Automated Processing

The workflow automatically:

1. Detects the new document
2. Downloads the file
3. Extracts text content
4. Generates metadata
5. Splits the document into chunks
6. Generates embeddings
7. Stores vectors in Supabase

---

## Step 3 — Query the AI Assistant

Ask a question such as:

```
What revenue growth was reported in the document?
```

---

## Step 4 — AI Retrieval

The system will:

1. Convert the question into an embedding
2. Search the vector database
3. retrieve the most relevant document chunks
4. generate a contextual answer

---

## Example Output

```
The document reports a 20% revenue increase in the streaming division during 2024.
```

---

This demonstrates how **Retrieval-Augmented Generation (RAG)** enables accurate document-based question answering.
