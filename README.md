# Q&A-Chatbot

This code implements a Retrieval-Augmented Generation (RAG) Q&A system with PDF document support and chat history using Streamlit. Here's a summary of the main components and functionality:

## Key Components

### 1. Document Processing:
- Allows users to upload multiple PDF files.
- Uses PyPDFLoader to load documents and RecursiveCharacterTextSplitter to split them into chunks.

### 2. Embedding and Vector Store:
- Utilizes HuggingFaceEmbeddings with the "all-MiniLM-L6-v2" model for text embeddings.
- Creates a Chroma vector store from the document chunks.

### 3. Language Model:
- Uses ChatGroq with the "Gemma2-9b-It" model for question answering.

### 4. Retrieval System:
- Implements a history-aware retriever that considers chat history when formulating queries.

### 5. Question Answering Chain:
- Combines the retriever with a document chain to answer questions based on retrieved context.

### 6. Chat History Management:
- Maintains session-based chat history using ChatMessageHistory.

## Workflow
- The user uploads PDF files and enters a Groq API key.
- Documents are processed, split, and stored in a vector database.
- The user enters a question in the chat interface.
- The system uses the history-aware retriever to find relevant document chunks.
- The question-answering chain generates a response based on the retrieved context and chat history.
- The response is displayed, and the chat history is updated.

## Notable Features
- Session Management: Users can specify a session ID to maintain separate chat histories.
- Context-Aware Retrieval: The system reformulates questions based on chat history for more accurate retrieval.
- Configurable Model: Uses Groq's Gemma2-9b-It model, which can be easily switched to other models.

This implementation provides a sophisticated RAG system that can handle multiple documents, maintain conversation context, and provide accurate answers based on the uploaded content and chat history.
