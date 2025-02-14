# RAG Question Answering System

A **Retrieval-Augmented Generation (RAG)** based Question Answering system using **Ollama, ChromaDB, LangChain, and Streamlit**. This application allows users to upload PDFs, extract text chunks, store them in a vector database, and perform question-answering using Llama 3.1 with local inference.

## Features

- **PDF Document Processing**: Extracts and splits text into smaller chunks for better retrieval.
- **Vector Database**: Uses ChromaDB to store and retrieve relevant document embeddings.
- **Local Inference**: Utilizes **Ollama** for efficient local LLM responses.
- **Cross-Encoder Re-ranking**: Enhances retrieval accuracy with **Sentence Transformers**.
- **Streamlit UI**: Provides an interactive interface for document upload and Q&A.

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Pichikachandu/LLAM3_RAG.git
cd llm-rag
```

### 2. Set Up a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install langchain-community chromadb streamlit ollama PyMuPDF sentence-transformers
```

## Requirements

Install the following dependencies:

```bash
ruff==0.7.4  # Linter
ollama==0.3.3  # Local LLM inference
chromadb==0.5.20  # Vector Database
sentence-transformers==3.3.1  # CrossEncoder Re-ranking
streamlit==1.40.1  # Application UI
PyMuPDF==1.24.14  # PDF Document loader
langchain-community==0.3.7  # Utils for text splitting
```

## Setting Up Ollama

Ollama is used for local LLM inference. Install and pull the required models:

```bash
ollama pull nomic-embed-text:latest
ollama pull llama3.1:latest
```

Verify the installed models:

```bash
ollama list
```

Expected Output:

```
nomic-embed-text:latest    0a109f422b47    274 MB    3 hours ago
llama3.1:latest            46e0c10c039e    4.9 GB    3 hours ago
```

## Running the Application

1. Start Ollama in the background:

```bash
ollama serve
```

2. Run the Streamlit application:

```bash
streamlit run app.py
```

## Usage

- **Upload a PDF**: The system processes and stores document embeddings in ChromaDB.
- **Ask a Question**: Enter a query related to the document.
- **Retrieve Answers**: The system finds the most relevant text and generates an answer using Llama 3.1.
- **View Retrieved Documents**: See which text chunks were used for generating the answer.

## Folder Structure

```
rag-qna/
│── app.py                 # Main application file
│── requirements/
│   ├── requirements.txt    # Main dependencies
│   ├── requirements-dev.txt # Development dependencies
│── demo-rag-chroma/       # ChromaDB persistent storage
│── README.md              # Project documentation
```

## Contributing

Feel free to submit issues and pull requests to improve this project.

## License

This project is licensed under the MIT License.

