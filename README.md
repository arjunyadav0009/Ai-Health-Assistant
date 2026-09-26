# 🏋️ AI Health Assistant

An AI-powered health and nutrition assistant built with **Python, Streamlit, RAG (Retrieval-Augmented Generation), Hugging Face embeddings, FAISS, and LLMs**.

The application provides personalized health information based on user details such as **age, gender, weight, height, and activity level**. It calculates important health metrics such as **BMI, BMR, TDEE, and daily calorie requirements**, and uses a **Retrieval-Augmented Generation (RAG)** pipeline to provide answers based on nutrition information stored in a PDF knowledge base.

---

## 🚀 Features

* 👤 User health profile input
* ⚖️ BMI calculation
* 🔥 BMR calculation
* 🏃 TDEE calculation
* 🍎 Daily calorie requirement estimation
* 🥗 Nutrition and diet-related information
* 🤖 AI-powered responses
* 📚 Retrieval-Augmented Generation (RAG)
* 🔎 Semantic search using embeddings
* 🗂️ FAISS vector database
* 📄 PDF-based nutrition knowledge base
* 💻 Interactive Streamlit interface

---

## 🛠️ Technologies Used

### Programming Language

* **Python**

### Frontend / UI

* **Streamlit**

### AI & LLM

* **Large Language Models (LLMs)**
* **Hugging Face**
* **OpenAI-compatible API**

### RAG Pipeline

* **LangChain**
* **Hugging Face Embeddings**
* **FAISS**
* **Recursive Character Text Splitter**

### Data Source

* Nutrition PDF knowledge base

---

## 🧠 How the AI Health Assistant Works

The application combines traditional health calculations with an AI-powered RAG pipeline.

### 1. User Input

The user provides information such as:

* Gender
* Age
* Weight
* Height
* Activity level

The application uses this information to calculate health metrics.

### 2. Health Calculations

The application calculates:

**BMI (Body Mass Index)**

BMI is calculated using the user's height and weight.

**BMR (Basal Metabolic Rate)**

BMR estimates the number of calories the body requires at rest.

**TDEE (Total Daily Energy Expenditure)**

TDEE estimates the calories required based on the user's activity level.

### 3. Document Processing

The nutrition PDF is loaded and divided into smaller pieces called **chunks**.

For example:

```text
Nutrition PDF
      ↓
Extract text
      ↓
Split into chunks
      ↓
Create embeddings
      ↓
Store in FAISS
```

### 4. Embeddings

Each text chunk is converted into a numerical representation called an **embedding**.

The project uses:

```text
sentence-transformers/all-MiniLM-L6-v2
```

These embeddings allow the application to find information that is semantically related to the user's question.

### 5. RAG Retrieval

When the user asks a nutrition-related question:

```text
User Question
      ↓
Create Query Embedding
      ↓
Search FAISS Vector Database
      ↓
Retrieve Relevant Information
      ↓
Send Context to LLM
      ↓
Generate Answer
```

This approach allows the LLM to use relevant information from the project's nutrition knowledge base when generating responses.

---

## 📁 Project Structure

```text
Ai-Health-Assistant/
│
├── App.py
├── diet.py
├── rag.py
├── create_database.py
├── llm_test.py
├── prompt.md
├── requirements.txt
│
├── data/
│   └── nutrition.pdf
│
├── vector_db/
│   ├── index.faiss
│   └── index.pkl
│
└── .gitignore
```

---

## 📌 File Description

### `App.py`

Main Streamlit application.

It provides the user interface and connects the health calculations and AI/RAG functionality.

### `diet.py`

Contains the health and calorie-related calculations such as:

* BMI
* BMR
* TDEE
* Calorie requirements

### `rag.py`

Contains the Retrieval-Augmented Generation functionality.

It handles:

* Loading the vector database
* Creating embeddings
* Retrieving relevant information
* Connecting retrieved context with the LLM

### `create_database.py`

Creates the FAISS vector database from the nutrition PDF.

### `llm_test.py`

Used for testing the LLM/API connection.

### `data/nutrition.pdf`

The nutrition knowledge source used by the RAG system.

### `requirements.txt`

Contains the Python dependencies required to run the project.

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/arjunyadav0009/Ai-Health-Assistant.git
```

### 2. Open the project

```bash
cd Ai-Health-Assistant
```

### 3. Create a virtual environment

```bash
python -m venv .venv
```

### 4. Activate the virtual environment

On macOS/Linux:

```bash
source .venv/bin/activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔐 Environment Variables

The project uses environment variables for API credentials.

Create a `.env` file in the project root:

```text
HF_TOKEN=your_huggingface_token
```

**Do not upload `.env` to GitHub.**

The `.env` file is included in `.gitignore` to keep API credentials private.

---

## ▶️ Run the Application

Start the Streamlit application using:

```bash
streamlit run App.py
```

After running the command, Streamlit will provide a local URL similar to:

```text
http://localhost:8501
```

Open this URL in your browser to use the application.

---

## 🔄 RAG Architecture

The project follows this basic RAG architecture:

```text
              Nutrition PDF
                   │
                   ▼
            Document Loader
                   │
                   ▼
             Text Chunking
                   │
                   ▼
              Embeddings
                   │
                   ▼
             FAISS Vector DB
                   │
                   │
User Question ─────┘
       │
       ▼
Query Embedding
       │
       ▼
Similarity Search
       │
       ▼
Relevant Context
       │
       ▼
      LLM
       │
       ▼
  AI Generated Answer
```

---

## 🎯 Project Objectives

The main objectives of this project are:

* To build an interactive AI-based health assistant.
* To calculate basic health and calorie-related metrics.
* To understand and implement Retrieval-Augmented Generation.
* To use embeddings for semantic search.
* To store and retrieve document information using FAISS.
* To connect retrieved information with an LLM.
* To build an easy-to-use interface using Streamlit.

---

## 🔮 Future Improvements

Some possible future improvements include:

* Personalized meal recommendations
* Weekly diet plans
* Food calorie database
* User authentication
* Chat history
* Improved nutrition knowledge base
* Multiple PDF/document support
* Cloud deployment
* Mobile-friendly interface
* Integration with fitness and health APIs

---

## ⚠️ Disclaimer

This project is created for **educational and informational purposes**.

The health and nutrition information provided by the application should not be considered a substitute for professional medical or dietary advice. Users should consult qualified healthcare professionals for personalized medical guidance.

---

## 👨‍💻 Author

**Arjun Kumar**

B.Tech Computer Science & Engineering

GitHub: [arjunyadav0009](https://github.com/arjunyadav0009)

---

## ⭐ Project

If you find this project useful or interesting, consider giving the repository a ⭐ on GitHub.
