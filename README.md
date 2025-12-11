
### Run containers
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


## How to create a model with pdf files as source

### Create a Knowledge Base
Open WebUI supports uploading documents (PDF, Markdown, TXT) into collections:
- In the WebUI sidebar, go to Workspace.
- Open "Knowledge" tab and click New Knowledge (e.g., name it my-pdfs).
- Upload your PDF file(s).
- Each PDF is automatically chunked and indexed.
- You can upload multiple PDFs into one collection or create separate collections for different topics.

### Create Model
- In the WebUI sidebar, go to Models.
- Click "New Model"
- In model settings go to the "Knowledge"
- Add the created Knowledge
- In "Capabilities" tick appropriate checkboxes


## How to use pdf collection
 Attach Knowledge Base to a Chat
- Start a new conversation.
- Select your knowledge base by typing #my-pdfs or choosing it from the UI.
- Ask questions
- The model will use Retrieval‑Augmented Generation (RAG): it retrieves relevant text chunks from your PDF and feeds them into the LLM prompt.




