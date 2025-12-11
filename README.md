
# Run containers

```shell
docker compose up -d
```

### Pull models
- Llama 3.1 (8B or 70B) → strong general model
- Mistral 7B → fast, good reasoning
- nomic-embed-text → embeddings for PDF retrieval

```shell
docker exec -it ollama ollama pull llama3.1
docker exec -it ollama ollama pull mistral
docker exec -it ollama ollama pull nomic-embed-text
docker exec -it ollama ollama list
```

### Open UI
[Open WebUI](http://localhost:8080)

# 📘 Using PDF Files as a Knowledge Source in Open WebUI

This guide explains how to create a model that leverages PDF documents as a knowledge base in **Open WebUI**.

---

## 🚀 Step 1: Create a Knowledge Base
Open WebUI supports uploading documents (PDF, Markdown, TXT) into collections.

1. In the **WebUI sidebar**, go to **Workspace**.
2. Open the **Knowledge** tab and click **New Knowledge** (e.g., name it `my-pdfs`).
3. Upload your PDF file(s).
4. Each PDF is automatically **chunked and indexed** for retrieval.
5. You can upload multiple PDFs into one collection or create separate collections for different topics.

---

## 🧩 Step 2: Create a Model
1. In the **WebUI sidebar**, go to **Models**.
2. Click **New Model**.
3. In the model settings, open the **Knowledge** section.
4. Attach the previously created Knowledge Base.
5. In **Capabilities**, tick the appropriate checkboxes to enable RAG and other features.

---

## 💡 Step 3: Use the PDF Collection in a Chat
To query your PDFs:

1. Start a new conversation.
2. Select your knowledge base by typing `#my-pdfs` or choosing it from the UI.
3. Ask questions about the content of your PDFs.
4. The model will use **Retrieval‑Augmented Generation (RAG)**: it retrieves relevant text chunks from your PDF and feeds them into the LLM prompt for accurate answers.

---

## ✅ Summary
- **Knowledge Bases** let you upload and index PDFs.
- **Models** can be linked to these Knowledge Bases.
- In chats, attach the Knowledge Base to enable RAG and query your documents directly.

This setup allows your LLM to act as a powerful assistant that can answer questions based on your PDF files.