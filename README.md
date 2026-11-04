# Intelligent Multi-Tool AI Assistant

An AI-powered conversational assistant built using **LangGraph, LangChain, and Streamlit**. It combines PDF-based Retrieval-Augmented Generation (RAG) with multiple tools, allowing users to interact with documents, search the web, retrieve stock prices, and perform mathematical calculations.

## Features

- **PDF-Based RAG:** Upload PDFs and ask questions based on their content.
- **Web Search:** Retrieve information from the web using DuckDuckGo.
- **Stock Price Lookup:** Fetch stock market quotes using the Alpha Vantage API.
- **Calculator:** Perform addition, subtraction, multiplication, and division.
- **Conversation Memory:** Maintain chat history using SQLite checkpointing.
- **Multi-Thread Conversations:** Create new chats and switch between previous conversations.
- **Streaming Responses:** Display AI responses as they are generated.

## Tech Stack

- **Programming Language:** Python
- **LLM:** Groq (GPT-OSS-120B)
- **Frameworks:** LangChain, LangGraph
- **Frontend:** Streamlit
- **Embeddings:** Cohere Embeddings
- **Vector Database:** FAISS
- **PDF Processing:** PyPDFLoader
- **Database:** SQLite
- **Web Search:** DuckDuckGo Search
- **Stock API:** Alpha Vantage

## Project Structure

```text
├── app.py              # Streamlit frontend
├── backend.py          # LangGraph backend and tools
├── requirements.txt    # Project dependencies
├── .env.example        # Environment variable template
├── .gitignore          # Git ignored files
└── README.md            # Project documentation
```

## Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Windows:**
```bash
venv\Scripts\activate
```

**Mac/Linux:**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure API Keys

Create a `.env` file in the project root and add your API keys:

```env
GROQ_API_KEY=your_groq_api_key
COHERE_API_KEY=your_cohere_api_key
ALPHA_VANTAGE_API_KEY=your_alpha_vantage_api_key
```

Make sure to keep your `.env` file private and never upload it to GitHub.

### 5. Run the application

```bash
streamlit run app.py
```

The application will open in your browser.

## How It Works

1. Users upload a PDF through the Streamlit interface.
2. The PDF is processed, split into smaller chunks, and converted into embeddings.
3. FAISS stores the embeddings for efficient similarity-based retrieval.
4. LangGraph manages the conversation flow and determines when tools are required.
5. The assistant uses the appropriate tool to answer user queries.
6. SQLite maintains conversation checkpoints for individual chat threads.

## Future Improvements

- Persistent storage of PDF vector indexes.
- Support for multiple document formats.
- Improved source citations and document-based responses.
- Additional API integrations and AI tools.

## License

This project is licensed under the MIT License.
