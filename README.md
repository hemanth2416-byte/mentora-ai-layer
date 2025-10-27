# 🤖 Mentora v3.4.1 — AI Teaching Assistant  
### _Multimodal Learning Assistant with Voice, Vision, ChromaDB & FAISS_

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12%2B-blue?logo=python" alt="Python"/>
  <img src="https://img.shields.io/badge/Streamlit-App-red?logo=streamlit" alt="Streamlit"/>
  <img src="https://img.shields.io/badge/Ollama-LLM%20Engine-black?logo=ollama" alt="Ollama"/>
  <img src="https://img.shields.io/badge/ChromaDB-HTTP%20Mode-yellow?logo=database" alt="ChromaDB"/>
  <img src="https://img.shields.io/badge/FAISS-Vector%20Backup-green" alt="FAISS"/>
  <img src="https://img.shields.io/badge/Whisper-Speech%20Recognition-orange" alt="Whisper"/>
</p>

---

## 🧠 Overview
**Mentora** is an AI-powered teaching assistant built with **Streamlit**, **Ollama**, and **ChromaDB**.  
It helps users upload, listen, and interact with learning materials using **voice, video, and text**.  
When ChromaDB is unavailable, it automatically switches to a **FAISS** offline fallback.  

---

## ⚙️ Features
- 🎙️ **Voice-based learning** with Whisper & gTTS  
- 🧾 **File support:** PDF, DOCX, PPTX, HTML, CSV, Audio, Video  
- 🧠 **RAG pipeline** with ChromaDB (HTTP) or FAISS fallback  
- 📊 **Learning analytics** — keyword trends & topic summaries  
- 💾 **Session persistence & export** to Markdown or PDF  
- 🧑‍🏫 **Custom teaching personas:** Friendly Mentor, Coding Tutor, Motivational Coach, Strict Professor  

---

## 🚀 Setup

### 🧩 1. Clone Repository
```bash
git clone https://github.com/hemanth2416-byte/mentora-ai-layer.git
cd mentora-ai-layer
🧩 2. Create Virtual Environment
bash
Copy code
python -m venv venv
venv\Scripts\activate     # On Windows
🧩 3. Install Dependencies
bash
Copy code
pip install -r requirements.txt
🧩 4. Run the App
bash
Copy code
streamlit run mentora_app.py
💡 Make sure Ollama and ChromaDB HTTP Server are running locally before launching the app:

bash
Copy code
ollama serve
chroma run --host localhost --port 8001
🧭 Architecture
mermaid
Copy code
flowchart TD
    subgraph UI["Streamlit Frontend"]
        U1[🎤 Voice Input]
        U2[📤 File Upload]
    end

    subgraph PROCESSING["Processing Pipeline"]
        P1[Whisper Speech-to-Text]
        P2[Text Extraction]
        P3[Embedding Generation via Ollama]
    end

    subgraph STORAGE["Vector Store"]
        C1[ChromaDB (HTTP Mode)]
        C2[FAISS (Offline Fallback)]
    end

    subgraph LLM["LLM Reasoning"]
        L1[Ollama LLaMA 3.2]
    end

    subgraph OUTPUT["Response & Insights"]
        O1[Answer Generation]
        O2[Voice Response (gTTS)]
        O3[Analytics Visualization]
    end

    U1 --> P1 --> P3
    U2 --> P2 --> P3
    P3 --> C1 & C2 --> L1
    L1 --> O1
    L1 --> O2
    L1 --> O3
🔗 Related Project
🧩 RAG-Pro Chatbot — A production-grade LangChain + LangGraph + LangSmith RAG application for enterprise retrieval.

Together, RAG-Pro + Mentora form a powerful ecosystem for intelligent learning and document analytics.

🧑‍💻 Author
Hemanth Kumar
DevOps | AI Engineer | Streamlit Developer

© 2025 Mentora — All rights reserved.

