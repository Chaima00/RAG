# Retrieval-Augmented Generation (RAG)

A Jupyter notebook demonstrating a basic Retrieval-Augmented Generation (RAG) workflow. It reads text from a car financing agreement, finds relevant passages for a user’s question, and asks a language model to answer using those passages as context.

## How it works

1. Reads `CAR FINANCING AGREEMENT.txt` and treats each line as a text chunk.
2. Uses an Ollama embedding model to create vector embeddings for the chunks.
3. Compares a question’s embedding with the stored embeddings to retrieve the five most similar chunks.
4. Sends the retrieved text and question to an Ollama language model, with instructions to answer only from the supplied context.

## Project files

- `RAG Model.ipynb` — notebook containing the RAG implementation.
- `CAR FINANCING AGREEMENT.txt` — text document used as the notebook’s source data.

## Requirements

- Python
- Jupyter Notebook or JupyterLab
- [Ollama](https://ollama.com/) running locally
- The Python packages `numpy` and `ollama`
- The models used by the notebook:
  - `hf.co/CompendiumLabs/bge-base-en-v1.5-gguf` — embeddings
  - `hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF` — responses

Install the Python packages:
```bash
pip install numpy ollama ```

Make sure Ollama is running and that both models are available to it before running the notebook. You can download them with:
ollama pull hf.co/CompendiumLabs/bge-base-en-v1.5-gguf
ollama pull hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF

Run the notebook
Clone or download this repository.
Keep CAR FINANCING AGREEMENT.txt in the same working directory as the notebook.
Start Jupyter and open RAG Model.ipynb.
Run the notebook cells in order, then enter a question when prompted.
Current limitations
The notebook treats each line of the source text as a separate chunk; answers depend on how the source document is formatted.
Retrieval uses cosine similarity and returns up to five chunks.
The notebook uses a local Ollama installation, so model availability and performance depend on your machine.
The notebook is a demonstration and does not include a web interface or persistent vector database.

Privacy
The notebook prints source text and retrieved passages in its output. Before publishing this repository, make sure the agreement and any saved notebook outputs are safe to share. Do not commit confidential documents or personal information. ``````
