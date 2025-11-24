# Utilizing LangChain to perform Retrieval Augmented Generation on Scientific Literature for Literature Review 

This repo is a DIY project to test if a smoother literature review can be done with a LLM. 

## Notebooks

### Main Notebook
- **`Zotero_rag.ipynb`**: Downloads PDFs from your Zotero library and enables RAG-based chat with your research papers
  - Uses Ollama (local Llama model) by default - no API costs, no token limits
  - Alternative: Switch to Groq for faster cloud-based inference
  - Automatically downloads PDFs from Zotero cloud storage
  - Creates searchable vector database from your papers

## Setup

### Prerequisites
1. **Install Ollama** (for local LLM):
   ```bash
   # Visit https://ollama.com/download or:
   brew install ollama  # macOS
   ```
   Then pull the model:
   ```bash
   ollama pull llama3.2
   ```

2. **Create `.env` file** with your credentials:
   ```
   ZOTERO_API_KEY=<your_zotero_api_key>
   ZOTERO_USER_ID=<your_zotero_user_id>
   LIBRARY_TYPE=user
   GROQ_API_KEY=<your_groq_api_key>  # Optional: only if using Groq instead of Ollama
   ```

### Getting API Keys
- **Zotero API Key**: Go to [Zotero Settings](https://www.zotero.org/settings/keys/new) and create a new private key
- **Zotero User ID**: Found in your account URL (e.g., `https://www.zotero.org/users/YOUR_USER_ID/`)
- **Groq API Key** (optional): [Free key from Groq Console](https://console.groq.com/playground)
- **OpenAI API Key** (optional): [OpenAI Platform](https://platform.openai.com/docs/api-reference/introduction) - requires credit card

## Installation

```bash
pip install -r requirements.txt
```

## Usage

1. Run the Zotero_rag.ipynb notebook
2. Execute cells in order to download PDFs and create vector database
3. Ask questions about your research papers in the chat cells at the end

