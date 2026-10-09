# Retrieval-Augmented Generation (RAG)

A Jupyter notebook demonstrating a basic Retrieval-Augmented Generation (RAG) workflow. It reads a car financing agreement, retrieves passages relevant to a question, and asks a language model to answer using those passages as context.

## How it works

1. Reads `CAR FINANCING AGREEMENT.txt` and treats each line as a text chunk.
2. Uses an Ollama embedding model to create a vector for each chunk.
3. Compares the question embedding with the stored vectors and retrieves the five most similar chunks.
4. Sends the question and retrieved text to an Ollama language model, instructed to answer only from the supplied context.

## Project files

- `RAG Model.ipynb` — notebook containing the RAG implementation.
- `CAR FINANCING AGREEMENT.txt` — source text used by the notebook.

## Requirements

- Python
- Jupyter Notebook or JupyterLab
- [Ollama](https://ollama.com/) installed and running locally
- The Python packages `numpy` and `ollama`
- The models used by the notebook:
  - `hf.co/CompendiumLabs/bge-base-en-v1.5-gguf` — embeddings
  - `hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF` — responses
  - `qwen2.5:3b` — comparison

Install the Python packages:

```bash
pip install numpy ollama
```

Make sure both models are available to Ollama. Start Ollama, then pull either model if needed:

```bash
ollama pull hf.co/CompendiumLabs/bge-base-en-v1.5-gguf
ollama pull hf.co/bartowski/Llama-3.2-1B-Instruct-GGUF
ollama pull qwen2.5:3b
```

## Run the notebook

From the project directory, start Jupyter:

```bash
jupyter notebook
```

Open `RAG Model.ipynb` and run the cells in order. The notebook expects `CAR FINANCING AGREEMENT.txt` and `CAR FINANCING AGREEMENT - COMPARISON.txt` to be in the same directory.

## Privacy

The notebook sends text and questions to the Ollama service configured in your environment. With a local Ollama instance, inference is performed locally; be mindful of the source document and your Ollama configuration when using sensitive data.

## License

No license is currently specified for this project. Without a license, others do not have explicit permission to reuse or distribute the project. Add a license file if you choose to grant those permissions.
