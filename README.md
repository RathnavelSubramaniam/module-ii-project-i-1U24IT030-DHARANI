# 🩺 AI-Powered HealthCare Assistant Using LLM and RAG

## 📌 Project Overview

The **AI-Powered Medical Assistant** is an LLM-based healthcare system that uses **Retrieval-Augmented Generation (RAG)** to answer general medical questions.

The system retrieves relevant information from a medical knowledge source and provides the retrieved context to an LLM. The LLM then generates a clear and relevant response based on the retrieved information.

The project is designed to make medical information easier and faster to access while reducing dependence on the LLM's pretrained knowledge.

## 🎯 Goal

To develop an AI-powered Medical Assistant that provides simple, clear, and relevant answers to general medical questions using an LLM and trusted medical information.

## 🎯 Objectives

* Answer general medical and health-related questions.
* Retrieve relevant information from medical documents.
* Explain medical terms and concepts in simple language.
* Generate clear and understandable responses.
* Use RAG to provide relevant medical context to the LLM.
* Improve factual grounding of generated answers.
* Evaluate the relevance and groundedness of responses.

## 🏥 Business Context

Healthcare professionals handle large amounts of medical information every day. Finding relevant information from medical books and research materials can be difficult and time-consuming.

The proposed Medical Assistant helps users quickly retrieve relevant medical information by using natural-language queries. The system combines document retrieval with an LLM to provide conversational answers and reduce the time spent manually searching through medical resources.

## 📚 Knowledge Source

The project uses the **Merck Manual of Diagnosis & Therapy, 19th Edition** as the medical knowledge source. The manual covers a wide range of medical topics, including disorders, tests, diagnoses, and drugs. The PDF used in the project contains **4,114 pages**.

## 🤖 Technologies Used

* **Python**
* **Mistral 7B Instruct**
* **Llama.cpp**
* **LangChain**
* **Sentence Transformers**
* **ChromaDB**
* **PyMuPDF**
* **Hugging Face Hub**
* **Retrieval-Augmented Generation (RAG)**
* **Google Colab**

The project uses the Mistral 7B Instruct GGUF model with Llama.cpp and loads the model through Hugging Face Hub.

## 🔄 RAG Architecture

The main workflow of the project is:

```text
                Medical PDF
                     ↓
              Document Loading
                     ↓
               Text Chunking
                     ↓
              Generate Embeddings
                     ↓
                 ChromaDB
              Vector Database
                     ↓
              User Medical Query
                     ↓
             Similarity Retrieval
                     ↓
          Relevant Medical Context
                     ↓
           Context + User Query
                     ↓
              Mistral 7B LLM
                     ↓
             Generated Answer
```

## 🔍 Retrieval-Augmented Generation

RAG is the core component of this project.

### 1. Document Loading

The medical PDF is loaded using **PyMuPDFLoader**.

### 2. Text Chunking

The large medical document is divided into smaller chunks using `RecursiveCharacterTextSplitter`.

The project uses:

* **Chunk size:** 512
* **Chunk overlap:** 20

### 3. Embedding Generation

The text chunks are converted into vector embeddings using the **`thenlper/gte-large`** embedding model.

### 4. Chroma Vector Database

The generated embeddings are stored in **ChromaDB**. This allows the system to search the medical knowledge base and retrieve relevant information for a user's question.

### 5. Retrieval

A similarity-based retriever is created to retrieve the **top 3 relevant document chunks** for a user query.

### 6. Context-Based Generation

The retrieved chunks are combined with the user's question and passed to the Mistral LLM. The system prompt instructs the model to use the provided context when generating the answer.

## 🧠 Prompt Engineering

A medical system prompt is used to guide the LLM.

The prompt instructs the model to:

* Use the provided medical context.
* Provide concise and relevant answers.
* Maintain a professional and safe tone.
* Include the source when applicable.
* Avoid providing information outside the available knowledge base.

If relevant information is not available in the retrieved context, the system is instructed to indicate that the information is outside its knowledge base.

## 💡 Example Questions

The RAG system was tested using medical questions from different areas:

1. **Critical Care** – What is the protocol for managing sepsis in a critical care unit?
2. **General Surgery** – What are the common symptoms of appendicitis?
3. **Dermatology** – What are the causes and treatments for sudden patchy hair loss?
4. **Neurology** – What treatments are recommended for brain injuries?

The system retrieves relevant medical content and generates responses for these questions.

## 📊 Evaluation

The generated RAG responses are evaluated using an **LLM-as-a-Judge** approach.

### Groundedness

Groundedness measures how well the generated answer is supported by the retrieved context.

The score ranges from:

* **1** – Not derived from the context
* **5** – Completely derived from the context

### Relevance

Relevance measures how well the generated answer addresses the user's question using the provided context.

The score ranges from:

* **1** – Not relevant
* **5** – Fully relevant

## 📋 Output

The generated questions and RAG responses are stored in a Pandas DataFrame containing:

* **Question**
* **Rag response**

The project generates responses for four medical questions.

## ✅ Benefits

* Provides quick access to medical information.
* Uses a medical reference as an external knowledge source.
* Reduces dependence on the LLM's pretrained knowledge.
* Retrieves relevant information before generating an answer.
* Makes medical information easier to understand.
* Supports evaluation of response relevance and groundedness.

## ⚠️ Limitations

* The system should not be used for medical diagnosis or treatment decisions.
* The quality of the answer depends on the retrieved information.
* The medical reference may not contain the latest medical information.
* LLM-generated responses may still contain errors.
* Professional medical advice is required for actual healthcare decisions.

## 🚀 Future Enhancements

* Use newer and regularly updated medical sources.
* Improve retrieval accuracy.
* Experiment with different embedding models.
* Improve response grounding.
* Reduce hallucinations.
* Add stronger medical safety controls.
* Develop a web-based interface.
* Add conversational memory for follow-up questions.
* Improve evaluation with additional metrics.

## 📝 Conclusion

The **AI-Powered Medical Assistant using RAG** successfully combines document retrieval and LLM-based generation to answer general medical questions. The system loads a medical reference, divides it into chunks, generates embeddings, stores them in ChromaDB, retrieves relevant information, and provides the retrieved context to the Mistral LLM for response generation.

The RAG approach provides a better foundation than relying only on the LLM's pretrained knowledge because responses are generated using retrieved medical information. The project also evaluates responses based on **groundedness and relevance**. Further improvements can focus on updated medical sources, retrieval accuracy, response safety, and factual reliability.

## 📁 Project Structure

```text
AI-Powered-Medical-Assistant/
│
├── AI_Powered_Healthcare_Assistant_Project.ipynb
├── LLM_Based_Medical_Assistant_final.ipynb
├── medical_diagnosis_manual.pdf
├── medical_db/
└── README.md
