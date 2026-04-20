# Retrieval-Augmented Generation (RAG) Implementation

This project implements a Retrieval-Augmented Generation (RAG) pipeline using LangChain. It is designed to ingest data from multiple formats (Text and PDF), process them into structured documents, and prepare them for downstream RAG tasks like embedding and retrieval.

## 🚀 Features

- **Multi-format Ingestion**: Load data from both `.txt` and `.pdf` files.
- **Efficient Processing**: Uses `DirectoryLoader` with specific class loaders (`TextLoader`, `PyPDFLoader`) for reliable parsing.
- **Progress Tracking**: Integrated `tqdm` to monitor document loading progress in large directories.
- **Structured Metadata**: Captures source paths and relevant metadata for every ingested document.

## 📁 Project Structure

```text
├── data/               # Project data directory
│   ├── text_files/     # Plain text source files
│   └── pdf/            # PDF source files
├── notebook/           # Jupyter notebooks for development
│   └── document.ipynb  # Main experimentation and pipeline logic
├── .gitignore          # System and data files to ignore (PDFs/TXTs ignored by default)
├── requirements.txt    # Python dependencies
└── README.md           # Project documentation
```

## 🛠️ Installation

1. **Clone the repository**:
   ```bash
   git clone <your-repository-url>
   cd Retrieval-Augmented-Generation-RAG-
   ```

2. **Set up a virtual environment**:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## 📖 Usage

### Data Ingestion
The pipeline currently supports loading all documents from a directory. To load your documents:

1. Place your text files in `data/text_files/`.
2. Place your PDF files in `data/pdf/`.
3. Run the ingestion cells in `notebook/document.ipynb`.

```python
from langchain_community.document_loaders import DirectoryLoader, TextLoader

# Load all text files
loader = DirectoryLoader("../data/text_files", glob="*.txt", loader_cls=TextLoader)
documents = loader.load()
```

## 🛠️ Tech Stack

- **Framework**: [LangChain](https://github.com/langchain-ai/langchain)
- **Document Loading**: LangChain Community Loaders (`PyPDFLoader`, `TextLoader`)
- **Environment**: Jupyter Notebook / Python 3.10+
- **Utilities**: `tqdm` for progress bars

## 📝 License
This project is for educational purposes.
