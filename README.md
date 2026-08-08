# AI-Powered Healthcare Assistant Using RAG

## 📌 Project Overview

The **AI-Powered Healthcare Assistant** is a Retrieval-Augmented Generation (RAG) based system that helps users get general medical information through natural-language questions. The system retrieves relevant information from a medical knowledge source and uses an LLM to generate clear and understandable answers.

The system is designed to support access to medical information and **does not replace professional medical diagnosis or treatment**.

## 🎯 Goal

To develop an AI-based Healthcare Assistant that provides simple, clear, and relevant answers to general medical questions using trusted medical information.

## 🎯 Objectives

* Answer general medical and health-related questions.
* Retrieve relevant information from medical documents.
* Explain medical terms and concepts in simple language.
* Generate useful responses using an LLM.
* Provide medical information through conversational interaction.
* Improve the reliability of answers using external medical knowledge.

## 📚 Knowledge Source

The project uses the **Merck Manual of Diagnosis & Therapy** as the medical knowledge source. The information from the medical document is processed and used for retrieving relevant content.

## 🛠️ Technologies Used

* Python
* LangChain
* Mistral 7B Instruct
* Llama.cpp
* Sentence Transformers
* ChromaDB
* PyMuPDF
* Hugging Face
* Google Colab
* Retrieval-Augmented Generation (RAG)

## 🔄 Project Workflow

```text
Medical PDF
     ↓
Load Document
     ↓
Split into Chunks
     ↓
Generate Embeddings
     ↓
Store in ChromaDB
     ↓
User Medical Query
     ↓
Retrieve Relevant Information
     ↓
Send Context to LLM
     ↓
Generate Final Response
```


## ⚙️ Implementation

### 1. Document Loading

The medical document is loaded using **PyMuPDFLoader**.

### 2. Text Splitting

The document is divided into smaller chunks using **RecursiveCharacterTextSplitter** to make information retrieval easier.

### 3. Embeddings

Sentence Transformer is used to convert the document chunks into numerical vector representations.

### 4. Vector Database

The generated embeddings are stored in **ChromaDB**. It helps retrieve information that is relevant to the user's question.

### 5. Response Generation

The retrieved information is provided as context to the **Mistral 7B LLM**, which generates the final response.

## 💡 Example Queries

The assistant can answer questions such as:

* What are the symptoms of appendicitis?
* What causes sudden patchy hair loss?
* What treatments are recommended for brain injuries?
* What is the recommended treatment protocol for sepsis?

## ✅ Benefits

* Provides quick access to medical information.
* Reduces the need to search lengthy medical documents manually.
* Uses external medical knowledge for generating responses.
* Provides conversational question answering.
* Makes medical information easier to understand.

## ⚠️ Limitations

* The system is intended for general medical information only.
* It should not be used for medical diagnosis or treatment decisions.
* The generated response may not always be completely accurate.
* Medical information may change over time.

## 🚀 Future Enhancements

* Add more updated and trusted medical sources.
* Improve retrieval accuracy.
* Improve response evaluation and factual grounding.
* Add stronger medical safety controls.
* Develop a web-based user interface.
* Support longer conversational context.

## 📝 Conclusion

The **AI-Powered Healthcare Assistant** demonstrates how RAG and LLM technology can be used to provide quick and understandable medical information. By retrieving relevant content from a medical knowledge source and providing it to the LLM, the system can generate more context-based responses. Overall, the project shows the potential of AI in supporting access to healthcare information, while professional medical advice remains essential for diagnosis and treatment.
