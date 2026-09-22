# StudyHub – AI-Powered Personalized Learning Assistant

## Overview

StudyHub is an AI-powered personalized learning assistant that helps students understand and revise their own study materials more efficiently.

Instead of manually searching through lengthy PDFs and notes, students can upload their study material and interact with it through an intelligent question-answering experience. StudyHub processes the uploaded content, retrieves relevant information using a Retrieval-Augmented Generation (RAG) pipeline, and uses an AI model to generate context-based responses.

The goal of StudyHub is simple: **turn existing study material into an interactive learning experience.**

---

## Problem Statement

Students often spend significant time searching through lengthy study materials to find specific concepts, definitions, and explanations. Traditional document readers provide access to information but do not provide an interactive way to understand the content.

Students need a learning assistant that can work directly with their own study materials and provide relevant answers without requiring them to manually search through every page.

---

## Proposed Solution

StudyHub provides an AI-powered interface where students can upload their study materials and ask questions about the content.

The application uses Retrieval-Augmented Generation (RAG) to:

1. Accept educational documents such as PDFs.
2. Extract and process the document content.
3. Split the content into meaningful sections.
4. Convert the content into searchable representations.
5. Retrieve the most relevant sections for a user's question.
6. Provide the retrieved context to the AI model.
7. Generate a context-based answer for the student.

This approach helps keep responses grounded in the uploaded learning material.

---

## Key Features

### Document-Based Learning

Upload study materials and interact with their content through the application.

### AI Question Answering

Ask questions about the uploaded material and receive AI-generated responses based on the retrieved document context.

### Retrieval-Augmented Generation

StudyHub combines information retrieval with AI generation so that relevant document content can be retrieved before generating an answer.

### Personalized Learning Experience

Students can use their own notes and educational documents as the knowledge source for their learning sessions.

### Simple Web Interface

A straightforward interface allows students to upload documents and interact with the learning assistant without manually searching through long files.

---

## How StudyHub Works

```text
Student
   ↓
Upload Study Material
   ↓
Document Processing
   ↓
Text Extraction
   ↓
Text Chunking
   ↓
Embedding Generation
   ↓
Vector Database
   ↓
Student Asks a Question
   ↓
Relevant Context Retrieval
   ↓
LLM
   ↓
Context-Based Answer
```

---

## RAG Architecture

StudyHub uses a Retrieval-Augmented Generation workflow.

### 1. Document Ingestion

The uploaded PDF is processed and its text content is extracted.

### 2. Text Processing

The extracted content is divided into smaller meaningful sections so that relevant information can be retrieved efficiently.

### 3. Embeddings

The processed text is converted into vector representations using an embedding model.

### 4. Vector Storage

The generated embeddings are stored in a vector database for similarity-based retrieval.

### 5. Query Processing

When the student asks a question, the question is converted into a searchable representation.

### 6. Context Retrieval

The system retrieves the most relevant sections from the uploaded study material.

### 7. AI Generation

The retrieved context is provided to the language model, which generates the final response.

---

## Technology Stack

| Layer               | Technology                     |
| ------------------- | ------------------------------ |
| Backend             | Python, FastAPI                |
| AI                  | Large Language Model           |
| RAG                 | Retrieval-Augmented Generation |
| Embeddings          | FastEmbed / BGE-small-en-v1.5  |
| Vector Database     | ChromaDB                       |
| Document Processing | PyPDF                          |
| Frontend            | HTML, CSS, JavaScript          |
| Database            | SQLite                         |
| Server              | Uvicorn                        |
| Version Control     | Git & GitHub                   |
| Deployment          | Vercel                         |

---

## Project Architecture

StudyHub follows a modular architecture where the frontend communicates with the FastAPI backend.

The backend handles document processing, database operations, retrieval, and AI-related functionality.

```text
Frontend
   │
   ↓
FastAPI Backend
   │
   ├── Document Processing
   │
   ├── RAG Pipeline
   │      ├── Embeddings
   │      ├── Vector Retrieval
   │      └── Context Generation
   │
   ├── LLM Integration
   │
   └── SQLite Database
```

---

## Project Structure

```text
studyhub/
│
├── app/
│   ├── main.py
│   ├── llm.py
│   ├── rag.py
│   └── database.py
│
├── templates/
│   └── index.html
│
├── static/
│   ├── style.css
│   └── script.js
│
├── requirements.txt
├── .gitignore
└── README.md
```

> The `.env` file containing secret credentials and the local virtual environment are kept outside the repository and should not be committed to GitHub.

---

## Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-github-repository-url>
cd studyhub
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

### 3. Activate the Virtual Environment

Windows:

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure Environment Variables

Create a `.env` file in the project directory and add the required API credentials.

Example:

```env
GROQ_API_KEY=your_api_key_here
```

Never commit the actual `.env` file or API keys to GitHub.

---

## Running the Application

Start the FastAPI application using Uvicorn:

```bash
uvicorn app.main:app --reload
```

The application can then be accessed through the local URL provided by the FastAPI/Uvicorn server.

---

## Example Usage

A student can upload a study document such as a Cloud Computing PDF and ask questions such as:

* What are the five essential characteristics of cloud computing?
* What are the three cloud service models?
* What are the four cloud deployment models?

StudyHub retrieves relevant information from the uploaded material and generates an answer using the retrieved context.

---

## Deployment

StudyHub can be deployed as a web application so that users can access the application through a browser.

The project source code is maintained using GitHub, and the deployed application can be connected to the GitHub repository for subsequent updates.

---

## Future Enhancements

* Support for additional document formats.
* More personalized learning recommendations.
* Interactive quizzes generated from uploaded study material.
* Improved learning analytics.
* Additional AI-powered study and revision features.

---

## Why StudyHub?

StudyHub focuses on making learning more interactive without requiring students to replace their existing study materials.

By combining document processing, vector retrieval, RAG, and AI generation, StudyHub transforms static educational content into an interactive learning assistant.

---

## License

This project is licensed under the MIT License.
