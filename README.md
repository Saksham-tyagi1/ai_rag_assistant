# **AI RAG Assistant**

## **📌 Project Overview**
The **AI RAG Assistant** is an intelligent chatbot designed to assist sales representatives by retrieving relevant information using **Retrieval-Augmented Generation (RAG)**. It integrates **OpenAI GPT models, Qdrant Vector Database, and MongoDB** for efficient information retrieval and conversational AI capabilities.

---

## **🚀 Features**
- **Conversational AI:** Uses OpenAI's `gpt-4o-mini` for natural language processing.
- **Vector Search:** Utilizes Qdrant for storing and retrieving vectorized embeddings of documents.
- **Chat History Management:** Saves and retrieves chat history using MongoDB.
- **Streamlit UI:** Provides an interactive chat interface.
- **Environment Variable Management:** Uses `.env` file for secure API key storage.

---

## **🛠️ Tech Stack**
- **Programming Language:** Python
- **Frameworks & Libraries:** LangChain, OpenAI API, Qdrant Client, Streamlit, MongoDB, Dotenv
- **Database:** Qdrant (Vector DB), MongoDB (Chat history storage)

---

## **📂 Project Structure**
```bash
ai_rag_assistant/
│── app.py                # Streamlit frontend interface
│── chatbot.py            # AIConsultant class for chatbot logic
│── db.py                 # Database connection and vector store management
│── .env                  # Environment variables (API keys)
│── requirements.txt      # Python dependencies
│── venv/                 # Virtual environment (not included in GitHub)
│── README.md             # Documentation
```

---

## **🛠️ Installation & Setup**

### **🔹 Step 1: Clone the Repository**
```bash
git clone https://github.com/YOUR_USERNAME/ai_rag_assistant.git
cd ai_rag_assistant
```

### **🔹 Step 2: Create and Activate Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate     # Windows
```

### **🔹 Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

### **🔹 Step 4: Set Up Environment Variables**
Create a `.env` file and add the following credentials:
```
OPENAI_API_KEY="your_openai_api_key"
MONGODB_CNX="your_mongodb_connection_string"
QDRANT_URL="your_qdrant_url"
QDRANT_API_KEY="your_qdrant_api_key"
```

---

## **🚀 Running the Application**

### **🔹 Step 1: Start the Streamlit App**
```bash
streamlit run app.py
```

### **🔹 Step 2: Access the Web UI**
Once running, open your browser and go to:
- **Local URL:** `http://localhost:8501`
- **Network URL:** Provided in the terminal

---

## **🛠️ How It Works**
### **1️⃣ Chatbot Initialization**
- The **`AIConsultant`** class initializes the chatbot with a session ID and username.
- It loads the **OpenAI GPT model** and connects to **Qdrant (Vector DB) and MongoDB**.

### **2️⃣ Query Processing**
- The chatbot **rephrases** user queries for better understanding.
- It retrieves relevant **vectorized documents** using Qdrant.
- Generates a **contextual response** using OpenAI's API.

### **3️⃣ Chat Storage**
- All conversations are stored in **MongoDB** for maintaining chat history.

---

## **📌 API Integrations**
- **OpenAI GPT API** for generating responses.
- **Qdrant API** for vector-based document retrieval.
- **MongoDB Atlas** for storing chat history.

---

## **⚡ Troubleshooting**
### **1️⃣ OpenAI API Key Error (401 Unauthorized)**
**Solution:** Ensure your API key is correct and set in `.env`.
```bash
echo $OPENAI_API_KEY  # Check if the key is loaded
```

### **2️⃣ Qdrant Collection Not Found (404 Error)**
**Solution:** The collection must be created before querying. Run:
```python
from db import get_qdrant_client
client = get_qdrant_client()
print(client.get_collections())
```

### **3️⃣ MongoDB Connection Issues**
**Solution:** Ensure MongoDB Atlas credentials are correct.
- Check if the cluster is active in [MongoDB Atlas](https://cloud.mongodb.com/).

---

## **📌 Contributing**
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`
3. Commit changes: `git commit -m "Added new feature"`
4. Push to GitHub: `git push origin feature-branch`
5. Open a Pull Request.

---

## **📜 License**
This project is licensed under the **MIT License**.

---

## **💡 Credits**
Developed by Saksham Tyagi.

---

## **📧 Contact**
For questions, contact: **sakshamtyagi134@gmail.com**
