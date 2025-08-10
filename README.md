# 📚 Document Embedding and Retrieval System

## 🌟 Overview

This advanced Retrieval-Augmented Generation (RAG) system is a sophisticated document processing and question-answering platform that leverages state-of-the-art natural language processing techniques. The system combines intelligent document extraction, semantic embedding, vector search, and generative AI to provide accurate and contextual responses to user queries.

## 🌐 Deployed Version

Check out the live demo of the RAG Document QA System: [https://navidchatbot.streamlit.app/](https://navidchatbot.streamlit.app/)

## 🏗️ System Architecture

```mermaid
flowchart TD
    User(["User"]) <--> UI["Web Interface\n(Streamlit)"]
    API(["External Systems"]) <--> APIServer["API Server\n(FastAPI)"]
    
    subgraph Core["RAG System Core"]
        direction TB
        RAGEngine["RAG Engine"] <--> DocProcessor["Document Processor"]
        RAGEngine <--> VectorDB["Vector Database"]
        RAGEngine <--> LLM["Language Models"]
        RAGEngine <--> KG["Knowledge Graph"]
    end
    
    UI <--> Core
    APIServer <--> Core
    
    Documents[("Document\nCollection")] --> DocProcessor
    
    class RAGEngine,KG primary
    class User,API,Documents secondary
```

The system employs a modular architecture combining vector search with knowledge graph capabilities:

1. **Document Processor** intelligently extracts, chunks, and prepares documents for embedding
2. **Vector Database** provides efficient similarity search using state-of-the-art indexing
3. **Knowledge Graph** captures semantic relationships between document entities
4. **RAG Engine** orchestrates the retrieval and generation process
5. **Language Models** generate contextual responses based on retrieved information

The system is accessible through both a **Streamlit web interface** for direct user interaction and a **FastAPI server** for programmatic integration with other applications.

## 🚀 Key Features

### 1. Intelligent Document Processing
- Multi-format document support (PDF, DOCX, TXT, CSV, JSON)
- Adaptive text chunking strategies
- Metadata extraction
- Configurable chunk sizes

### 2. Advanced Embedding
- Supports multiple embedding models
- Sentence Transformers integration
- HuggingFace Transformers compatibility
- GPU and CPU support

### 3. Semantic Search Capabilities
- Vector database with multiple backends (FAISS, Keyword)
- Hybrid search modes (semantic, keyword, hybrid)
- Metadata-based filtering
- Efficient similarity search

### 4. Knowledge Graph Integration
- Implicit knowledge graph creation through semantic embeddings
- Relationship mapping between document chunks
- Context-aware document retrieval
- Enhanced reasoning capabilities

### 5. Generative Question Answering
- Multiple LLM backends (OpenAI, HuggingFace, Local)
- Chain-of-Thought reasoning
- Customizable prompt templates
- Contextual response generation

## 📦 Prerequisites

- Python 3.8+
- PyTorch
- Sentence Transformers
- Vector Database Libraries

## 🔧 Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/document-embedding-system.git

# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

## 🌈 Components

- **Document Processor**: Intelligent text extraction and chunking
- **Embedding Model**: Convert text to semantic vectors
- **Vector Database**: Efficient document storage and retrieval
- **RAG Engine**: Combine retrieval and generation
- **LLM Integration**: Multiple language model backends
- **Knowledge Graph**: Enhance retrieval with entity relationships

## 💡 Usage Example

```python
# Initialize components
from document.processor import DocumentProcessor
from embedding.model import create_embedding_model
from rag.engine import create_rag_engine

# Process documents
processor = DocumentProcessor()
chunks, metadata = processor.process_file('path/to/document.pdf')

# Create RAG engine
rag_engine = create_rag_engine()

# Add documents
rag_engine.add_documents(chunks, metadata)

# Query documents
response = rag_engine.generate_response("What are the key points?")
print(response)
```

## 🔬 Knowledge Graph Features

The system creates an implicit knowledge graph through:
- Semantic embeddings that capture document relationships
- Context-aware document retrieval
- Ability to map connections between document chunks
- Reasoning that considers multiple document contexts

## 🚧 Roadmap

- [ ] Add more document type support
- [ ] Implement advanced semantic search
- [ ] Create REST API interface
- [ ] Add machine learning model fine-tuning
- [ ] Enhance knowledge graph visualization

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📊 Supported Interfaces

- Streamlit Web App
- FastAPI Backend
- CLI Tools
- Python Library

## 🛡️ Error Handling

- Robust error management
- Comprehensive logging
- Graceful failure mechanisms

## 📜 License

MIT License

## 📞 Contact

Navid Mirnouri - navid72m@gmail.com


## 🔗 Quick Links

- **Live Demo**: [https://navidchatbot.streamlit.app/](https://navidchatbot.streamlit.app/)
- **Repository**: [GitHub Project](https://github.com/yourusername/document-embedding-system)


---

**Note**: Ensure you have appropriate computational resources for processing large document collections.