# StudyHub – AI-Powered Personalized Learning Assistant

## Overview

## Project Description

StudyHub is an AI-powered personalized learning assistant designed to help students learn and understand their study materials more effectively. The application allows users to upload educational documents and ask questions based on their learning content.

The system uses **Retrieval-Augmented Generation (RAG)** to retrieve relevant information from uploaded documents and uses a **Large Language Model (LLM)** to generate clear and contextual answers. This helps students interact with their study materials using natural language instead of manually searching through lengthy documents.

---

## Features

* Upload and process study materials
* Ask questions related to uploaded documents
* AI-powered question answering using RAG
* Retrieves relevant information from study materials
* Generates contextual answers using an LLM
* Document text extraction and processing
* Semantic search using embeddings
* Vector-based document retrieval
* Simple and user-friendly interface
* Personalized learning experience
* Supports learning through natural-language questions

---

## Technologies Used

* Python
* FastAPI
* Uvicorn
* Retrieval-Augmented Generation (RAG)
* Large Language Model (LLM)
* FastEmbed
* BGE-small-en-v1.5 Embedding Model
* ChromaDB
* PyPDF
* HTML
* CSS
* JavaScript
* SQLite
* Python-dotenv

---

## Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd studyhub
```

### 2. Create Virtual Environment

```bash
python -m venv venv
```

### 3. Activate Virtual Environment

**Windows:**

```bash
venv\Scripts\activate
```

**Linux/Mac:**

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure Environment Variables

Create a `.env` file in the project root and add your required API key:

```env
GROQ_API_KEY=your_api_key
```

> Keep the `.env` file private and do not upload it to GitHub.

---

## Usage

Run the FastAPI application:

```bash
python -m uvicorn app.main:app --reload
```

Open the application in your browser:

```text
http://127.0.0.1:8000
```

---

## Steps

* Open the StudyHub application.
* Upload a study document such as a PDF.
* The system extracts the text from the document.
* The extracted content is divided into smaller chunks.
* FastEmbed generates embeddings for the document chunks.
* The embeddings are stored in ChromaDB.
* Enter a question related to the uploaded study material.
* The system converts the question into an embedding.
* Relevant document chunks are retrieved using semantic search.
* The retrieved information is provided as context to the LLM.
* The LLM generates a relevant and easy-to-understand answer.
* The answer is displayed to the user.

---

## Project Workflow

1. User opens the StudyHub application.
2. User uploads a study document.
3. The system extracts text from the uploaded document.
4. The extracted text is divided into smaller chunks.
5. FastEmbed generates vector embeddings for the chunks.
6. ChromaDB stores the document embeddings.
7. User enters a question.
8. The question is converted into an embedding.
9. ChromaDB performs semantic similarity search.
10. Relevant document chunks are retrieved.
11. Retrieved information is passed as context to the LLM.
12. The LLM generates a contextual response.
13. The generated answer is displayed to the user.

---

## RAG Architecture

```text
User
  |
  v
Upload Study Material
  |
  v
Text Extraction
  |
  v
Text Chunking
  |
  v
FastEmbed / BGE Embeddings
  |
  v
ChromaDB
  |
  |------ Document Retrieval
  |
  v
User Question
  |
  v
Question Embedding
  |
  v
Semantic Search
  |
  v
Relevant Context
  |
  v
LLM
  |
  v
Generated Answer
```

---

## Key Components

### Document Processing

StudyHub extracts text from uploaded PDF documents and divides the content into smaller chunks for efficient retrieval.

### Embeddings

FastEmbed with the **BGE-small-en-v1.5** embedding model converts text into numerical vector representations.

### Vector Database

**ChromaDB** stores and searches the generated embeddings to find information that is semantically relevant to the user's question.

### Retrieval-Augmented Generation

RAG combines document retrieval with an LLM. Instead of generating an answer only from the model's general knowledge, the system first retrieves relevant information from the user's study materials.

### Large Language Model

The retrieved context is provided to an LLM, which generates the final natural-language response for the user.

---

## Project Structure

```text
studyhub/
│
├── app/
│   ├── main.py
│   ├── ...
│   └── ...
│
├── venv/
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

> `venv/` and `.env` should not be uploaded to GitHub.

---

## Future Work

* Support additional document formats such as DOCX and PPTX.
* Add personalized study plans based on user learning goals.
* Add quiz and question-generation features.
* Add automatic summaries and key-point extraction.
* Add user-specific learning history and progress tracking.
* Support multiple languages for learning materials.
* Improve retrieval accuracy using advanced embedding and reranking techniques.
* Add authentication and user profiles.
* Deploy the application as a cloud-based learning platform.

---

## Contributing

Contributions are welcome! Feel free to fork the repository, improve the project, and submit a Pull Request.

---

## License

This project is licensed under the MIT License.
