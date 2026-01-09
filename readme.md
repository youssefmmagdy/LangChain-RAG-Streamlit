# 📄 RAG Chatbot with LangChain, HuggingFace & Streamlit

A **Retrieval-Augmented Generation (RAG)** chatbot that allows users to upload a PDF and ask questions about its content.
The application is built with **LangChain** for RAG orchestration, **FAISS** for vector similarity search, **HuggingFace Inference API (Gemma 2B)** for generation, and **Streamlit** for an interactive web interface.

🚀 **Live Demo:**
![Live Demo](assets/demo.gif)

---
**Link**
👉 [https://langchain-rag-app.streamlit.app/)
---

## ✨ Features

* 📂 Upload any **PDF document**
* 🔍 Automatic text extraction and chunking
* 🧠 Semantic search using vector embeddings
* 🤖 Context-aware answers using **Gemma 2B**
* 💬 Chat-style interface with conversation history
* ⚙️ Adjustable chunk size, overlap, temperature, and response length

---

## 🧠 How It Works (RAG Pipeline)

1. **PDF Upload**
   Users upload a PDF file through the Streamlit interface.

2. **Text Extraction**
   Text is extracted from the PDF using `pypdf`.

3. **Chunking**
   The extracted text is split into overlapping chunks using `RecursiveCharacterTextSplitter`.

4. **Embeddings**
   Each chunk is converted into a vector embedding using:

   ```
   sentence-transformers/all-MiniLM-L6-v2
   ```

5. **Vector Store (FAISS)**
   The embeddings are stored in a FAISS vector database for fast similarity search.

6. **Retrieval**
   When a user asks a question, the most relevant chunks are retrieved from the vector store.

7. **Generation**
   The retrieved context is passed to the **Gemma 2B** model via HuggingFace Inference API.

8. **Response**
   The model generates a grounded, context-aware answer that is shown in the chat UI.

---

## 🏗️ Tech Stack

| Component       | Technology                         |
| --------------- | ---------------------------------- |
| Frontend / UI   | Streamlit                          |
| RAG Framework   | LangChain                          |
| Vector Database | FAISS                              |
| Embeddings      | HuggingFace Sentence Transformers  |
| LLM             | Google Gemma 2B (HF Inference API) |
| PDF Parsing     | pypdf                              |

---

## 📦 Local Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # macOS / Linux
venv\\Scripts\\activate      # Windows
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Run the Application

```bash
streamlit run app.py
```

---

## 🔐 Authentication Note

This project is already configured with a HuggingFace token internally for deployment.
**Users running the live demo or cloning the repository do not need to provide their own HuggingFace API token.**

---

## 🧪 Configuration Options

The following parameters can be adjusted from the sidebar:

* **Chunk Size** – Size of text chunks used for embeddings
* **Chunk Overlap** – Overlap between consecutive chunks
* **Max Output Tokens** – Maximum length of the generated answer
* **Temperature** – Controls randomness of model responses

---

## 📁 Project Structure

```
.
├── app.py              # Main Streamlit application
├── requirements.txt    # Python dependencies
└── README.md           # Project documentation
```

---

## 🚀 Deployment

The application is deployed using **Streamlit Community Cloud**.

🔗 **Live Application:**
[https://langchain-rag-app.streamlit.app/)

---

## ⚠️ Limitations

* Large PDF files may increase processing time
* Quality of answers depends on extracted text quality
* Context is limited to retrieved chunks

---

## 📌 Future Improvements

* Support for multiple documents
* Persistent vector storage
* Source citations for answers
* Streaming token-level responses
* Improved UI and chat controls

---

## ❤️ Acknowledgements

* LangChain
* HuggingFace
* Streamlit
* FAISS
* Sentence Transformers

---

### ⭐ If you find this project useful, feel free to star the repository!
