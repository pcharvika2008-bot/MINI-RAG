# 📚 Mini RAG: Document Store + Retrieval

A simple Retrieval-Augmented Generation (RAG) application built using **Python, Streamlit, ChromaDB, Sentence Transformers, and Ollama**.

This project allows users to upload PDF documents, split the extracted text into chunks, generate embeddings, store them in a vector database, and ask questions about the uploaded content using a locally running Large Language Model (LLM).

## 🚀 Features

* 📄 **PDF Upload:** Upload text-based PDF documents.
* ✂️ **Text Chunking:** Split document content into smaller chunks.
* 🧠 **Embedding Generation:** Convert text into vector embeddings using Sentence Transformers.
* 🗄️ **Vector Database:** Store and retrieve document chunks using ChromaDB.
* 🔍 **Semantic Search:** Retrieve relevant chunks based on user questions.
* 🤖 **AI Question Answering:** Generate answers using Ollama.
* ⚙️ **Custom Settings:** Adjust chunk size, number of retrieved chunks, and the Ollama model.
* 🔎 **Retrieved Context:** View the text chunks used to generate the answer.
* 💻 **Local Execution:** Run the application locally without relying on a hosted LLM API.

## 🛠️ Technologies Used

| Technology            | Purpose                              |
| --------------------- | ------------------------------------ |
| Python                | Core programming language            |
| Streamlit             | Interactive web interface            |
| PyPDF                 | Extract text from PDF documents      |
| Sentence Transformers | Generate text embeddings             |
| ChromaDB              | Store and retrieve vector embeddings |
| Ollama                | Run local language models            |
| Llama 3.2             | Default language model               |
| UUID                  | Generate unique document chunk IDs   |

## 🏗️ Project Workflow

1. Upload a PDF document.
2. Extract readable text from the PDF.
3. Divide the text into smaller chunks.
4. Generate embeddings for each chunk.
5. Store the chunks and embeddings in ChromaDB.
6. Enter a question related to the document.
7. Convert the question into an embedding.
8. Retrieve the most relevant chunks using vector similarity search.
9. Pass the retrieved context and question to Ollama.
10. Display the generated answer and retrieved context.

## 📂 Project Structure

```text
mini-rag-document-retrieval/
│
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
├── LICENSE
└── chroma_db/
```

The `chroma_db` directory is generated automatically when the application stores documents.

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/mini-rag-document-retrieval.git
```

Navigate to the project directory:

```bash
cd mini-rag-document-retrieval
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate the virtual environment on Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

If PowerShell blocks script execution, use Command Prompt instead:

```cmd
venv\Scripts\activate.bat
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Install Ollama

Download and install Ollama from:

https://ollama.com/download

Pull the default model:

```bash
ollama pull llama3.2
```

Make sure the Ollama service is running before using the application.

### 5. Run the application

```bash
streamlit run app.py
```

The Streamlit application will open in your browser, usually at:

```text
http://localhost:8501
```

## 💡 How to Use

1. Open the Mini RAG application.
2. Upload a text-based PDF file.
3. Adjust the chunk size in the sidebar if required.
4. Click **Process & Store PDF**.
5. Wait for the embeddings to be generated and stored.
6. Enter a question about the uploaded document.
7. Select the number of chunks to retrieve.
8. Click **Ask AI**.
9. View the generated answer.
10. Expand **View Retrieved Context** to inspect the retrieved text.

## 🧠 How RAG Works

Retrieval-Augmented Generation combines information retrieval with text generation.

**Document processing:**

* Extracts text from PDFs.
* Splits the text into manageable chunks.
* Converts chunks into embeddings.
* Saves the vectors and original text in ChromaDB.

**Retrieval:**

* Converts the user's question into an embedding.
* Searches the vector database for relevant text.
* Selects the most relevant chunks.

**Generation:**

* Combines retrieved chunks with the user's question.
* Sends the prompt to Ollama.
* Generates an answer based on the retrieved context.

## 📌 Default Configuration

| Setting          | Default Value    |
| ---------------- | ---------------- |
| Embedding Model  | all-MiniLM-L6-v2 |
| Ollama Model     | llama3.2         |
| Chunk Size       | 500 characters   |
| Retrieved Chunks | 3                |
| Vector Database  | ChromaDB         |
| Interface        | Streamlit        |

## ⚠️ Limitations

* Works with text-based PDFs; scanned documents may require OCR.
* Answers depend on the quality of extracted text and retrieved chunks.
* The current version stores chunks from multiple uploads in the same collection.
* It does not currently provide document-specific filtering or source page citations.
* Local model performance depends on the available system resources.
* The model may still generate inaccurate answers even when instructed to use only retrieved context.

## 🔮 Future Enhancements

* Support multiple PDF documents with document-specific retrieval.
* Add chat history and conversational memory.
* Display source page numbers for answers.
* Implement overlapping text chunking.
* Add a document deletion option.
* Improve retrieval with reranking.
* Support different embedding and language models.
* Add a document preview feature.
* Improve the interface with a modern chat layout.

## 🎯 Applications

* Academic document question answering
* Research paper exploration
* Study material analysis
* Personal PDF knowledge assistants
* Technical document search
* Local AI experimentation

## 👩‍💻 Author

**P. Charvika**

B.Tech – Computer Science and Engineering

## 📜 License

This project is available under the MIT License. See the `LICENSE` file for details.
